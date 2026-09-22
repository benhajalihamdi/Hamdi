---
tags:
  - AI
  - AI/Gen_AI
  - course
Date /Time: "{date} {time}"
title:
draft: true
---
FashionMNIST is designed to be a "Hello World" dataset for image classification problems. The small size of the black and white images (28 x 28 pixels) also makes it a great starting point for image generation.

```
train_set =torchvision.datasets.FashionMNIST("./data/", download=True,transform=transforms.Compose([transforms.ToTensor()]))
NUM_CLASSES = 10
```
Using [[the ToTensor function]] For further processing.
## Creating  A function to Show Images 

Using torcvision like used in the [[MNIST data set or Hello World Notes]] and the transforms we can create a function to show the images .

```
def show_images(dataset, num_samples=10):
    for i, img in enumerate(dataset):
        if i == num_samples:
            return
        plt.subplot(1, num_samples, i + 1)
        plt.imshow(torch.squeeze(img[0]))
```

In U-Nest generally we halve the sier of the feature Map using [[Max Pooling]] and the doubled using [[Transposed Convolution]]

So we pick size for the image as a power of 2 (128,256,32...etc)

## Transforming and Loading the Data


```
def load_fashionMNIST(data_transform, train=True):
    return torchvision.datasets.FashionMNIST(
        "./",
        download=True,
        train=train,
        transform=data_transform,
    )


def load_transformed_fashionMNIST():
    data_transforms = [
        transforms.Resize((IMG_SIZE, IMG_SIZE)),
        transforms.ToTensor(),  # Scales data into [0,1]
        transforms.RandomHorizontalFlip(),
        transforms.Lambda(lambda t: (t * 2) - 1)  # Scale between [-1, 1]
    ]
```

The Block of code below represents the Downloading of the entirety of the data and the separation for such data into a train set and a test set

```
    data_transform = transforms.Compose(data_transforms)
    train_set = load_fashionMNIST(data_transform, train=True)
    test_set = load_fashionMNIST(data_transform, train=False)
    return torch.utils.data.ConcatDataset([train_set, test_set])
```

After which,, we will transformed The Data and load it using our functions.

```
data = load_transformed_fashionMNIST()
dataloader = DataLoader(data, batch_size=BATCH_SIZE, shuffle=True, drop_last=True)
```

# The U-Net Architecture

As seen in [[U-Nets]], the U-Net is fromed of two blocks a "encoder" and a "decoder" or a "Down Block" and an "Up Block"

## Down Block
Which is a typical Convolutional neural netword as seen in [[Fundamentals of deep learning NVIDIA course]],

In our architecture we will have A Conv2d that will apply convolution to the input 
A ReLu activation layer 
BatchNorm2d to apply [[batch normalization]] to a layer of neurons (Batch Normalization have learnable parameters => reusing this function is dangerous)
MaxPool2D which we woukd us to [[Max Pooling|Max Pool]] our feature map as it moves "Down" the network


The DownBlock bellow represents the steps we are applying to the Feature Map
```
class DownBlock(nn.Module):
    def __init__(self, in_ch, out_ch):
        kernel_size = 3
        stride = 1
        padding = 1

        super().__init__()
        layers = [
            nn.Conv2d(in_ch, out_ch, kernel_size, stride, padding),
            nn.BatchNorm2d(out_ch),
            nn.ReLU(),
            nn.Conv2d(out_ch, out_ch, kernel_size, stride, padding),
            nn.BatchNorm2d(out_ch),
            nn.ReLU(),
            nn.MaxPool2d(2)
        ]
        self.model = nn.Sequential(*layers)

    def forward(self, x):
        return self.model(x)
```

In the `forward` method, we describe how are various functions should be applied to an input

## The Up Block
The Up block increases the size of the feature Map accomplished by [[Transposed Convolution]] or simply by the ConvTranspose2d We Will Also Concatenating the output of a Up Block matching Down Bllock with the UpBlock's Input

```
class UpBlock(nn.Module):
    def __init__(self, in_ch, out_ch):
        # Convolution variables
        kernel_size = 3
        stride = 1
        padding = 1

        # Transpose variables
        strideT = 2
        out_paddingT = 1

        super().__init__()
        # 2 * in_chs for concatednated skip connection
        layers = [
            nn.ConvTranspose2d(2 * in_ch, out_ch, kernel_size, strideT, padding, out_paddingT),
            nn.BatchNorm2d(out_ch),
            nn.ReLU(),
            nn.Conv2d(out_ch, out_ch, kernel_size, stride, padding),
            nn.BatchNorm2d(out_ch),
            nn.ReLU()
        ]
        self.model = nn.Sequential(*layers)
    
    def forward(self, x, skip):
        x = torch.cat((x, skip), 1)
        x = self.model(x)
        return x
```

Here we don't have any Max Pooling because we are increasing the map. Instead we have transposed convolution layers

**MISSING TRAINING AND CODE TO BE WRITTEN

## the model Code




- input: 1 x 16 x 16
- down0: 16 x 16 x 16
    - down1: 32 x 8 x 8
        - down2: 64 x 4 x 4
            - dense_emb: 1024
        - up0: 64 x 4 x 4
    - up1: 64 x 8 x 8
- up2: 32 x 16 x 16
- out: 1 x 16 x 16


```
class UNet(nn.Module):
    def __init__(self):
        super().__init__()
        img_ch = IMG_CH
        down_chs = (16, 32, 64)
        up_chs = down_chs[::-1]  # Reverse of the down channels
        latent_image_size = IMG_SIZE // 4 # 2 ** (len(down_chs) - 1)

        # Inital convolution
        self.down0 = nn.Sequential(
            nn.Conv2d(img_ch, down_chs[0], 3, padding=1),
            nn.BatchNorm2d(down_chs[0]),
            nn.ReLU()
        )

        # Downsample
        self.down1 = DownBlock(down_chs[0], down_chs[1])
        self.down2 = DownBlock(down_chs[1], down_chs[2])
        self.to_vec = nn.Sequential(nn.Flatten(), nn.ReLU())
        
        # Embeddings
        self.dense_emb = nn.Sequential(            nn.Linear(down_chs[2]*latent_image_size**2, down_chs[1]),
            nn.ReLU(),
            nn.Linear(down_chs[1], down_chs[1]),
            nn.ReLU(),
            nn.Linear(down_chs[1], down_chs[2]*latent_image_size**2),
            nn.ReLU()
        )
        
        # Upsample
        self.up0 = nn.Sequential(
            nn.Unflatten(1, (up_chs[0], latent_image_size, latent_image_size)),
            nn.Conv2d(up_chs[0], up_chs[0], 3, padding=1),
            nn.BatchNorm2d(up_chs[0]),
            nn.ReLU(),
        )
        self.up1 = UpBlock(up_chs[0], up_chs[1])
        self.up2 = UpBlock(up_chs[1], up_chs[2])

        # Match output channels
        self.out = nn.Sequential(
            nn.Conv2d(up_chs[-1], up_chs[-1], 3, 1, 1),
            nn.BatchNorm2d(up_chs[-1]),
            nn.ReLU(),
            nn.Conv2d(up_chs[-1], img_ch, 3, 1, 1),
        )

    def forward(self, x):
        down0 = self.down0(x)
        down1 = self.down1(down0)
        down2 = self.down2(down1)
        latent_vec = self.to_vec(down2)

        up0 = self.up0(latent_vec)
        up1 = self.up1(up0, down2)
        up2 = self.up2(up1, down1)
        return self.out(up2)
```

**NEED FURTHER UNDERSTANDING**


