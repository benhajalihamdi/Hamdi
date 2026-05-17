---
tags:
  - AI/Deep_Learning
Date /Time: "{date} {time}"
title:
---
## Dependencies /libraries
import torch
import torch.nn as nn
from torch.utils.data import Dataset, DataLoader
from torch.optim import Adam

import torchvision
import torchvision.transforms.v2 as transforms
import torchvision.transforms.functional as F
import matplotlib.pyplot as plt
## starting 
```
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
torch.cuda.is_available()
```
if the gpu is configered with cuda our device will be cuda if not the device is cpu 

```
train_set = torchvision.datasets.MNIST("./data/", train=True, download=True)
```

The [MNIST dataset](http://yann.lecun.com/exdb/mnist/) contains 70k photos of numbers from 0 to 9 and its answers as integers.
This line of code does the following
torchvision.dataset.MNIST("path",train=bool,download=bool)

`"./data/"` : This tells PyTorch where to save the files on your cloud server. It creates a folder named `data` in your current directory..
- `train=True`: This is the exact piece of syntax that divides the data. By default torchvision divides this data into 60k for training and 10k for testing
- `download=True` : This tells PyTorch to download the data if it doesnt exist in that speciphic path

pytorch dataset x
x[i] is a tuple (pair) that contains image (array) and the label for that image in this case (integer)
x.data has all the images (arrays or 2d tensors)
x.targets has all the labels (integers)

if train= False => we get the testing set (10k tuples in this case)

## Tensors!!!
```
trans = transforms.Compose([transforms.ToTensor()])
```
the transforms.Compose part of the code defines a "pipeline" of functions to execute for incoming data in this case ToTensoer function is sufficient 

[[the ToTensor function]] transforms normal images to tensors!
 this tensor has a .shape a .device and .dtype meaning how is it shaped and where is it processed (by default the cpu)) and the type of each of the "pixels" making up one tensor (torch.float32)

to move a tensor to be processed in the GPU we can use .cuda method or .to(device) if the gpu is recognized by pytorch, then the tensor will be processed by the device we have defined

## Viewing images using torchvision
```
 image = F.to_pil_image(x_0_tensor)
plt.imshow(image, cmap='gray') 
```
F.to_pil_image does the opposite of [[the ToTensor function]] 

The `plt` nickname stands for **Matplotlib**, which is Python’s standard data plotting and visualization library.

`cmap='gray'`: This argument stands for **Color Map**. Because MNIST digits are grayscale, you have to explicitly tell Matplotlib to display the numbers using a black-to-white gradient.

## DataLoader 

we basically going to load the data to train or validate with based on a  specific number of batches and each batch has a specific number of images / tensors ...etc. 

in this case we will load the data as a 32 batch sized shuffled for the training data and unshuffled for the testing data

## Making the model itself 

we will create a "Hello World" level model made from 4 components:

1. A [Flatten](https://www.google.com/url?q=https%3A%2F%2Fpytorch.org%2Fdocs%2Fstable%2Fgenerated%2Ftorch.nn.Flatten.html) used to convert n-dimensional data into a vector.
2. An input layer, the first layer of neurons
3. A hidden layer, another layer of neurons "hidden" between the input and output
4. An output layer, the last set of neurons which returns the final prediction from the model

input_size =28x28x1
```
layers =[
    nn.Flatten(),
    nn.Linear(input_size,512),
    nn.ReLu()
    nn.Linear(512,512)
    nn.ReLu()
    nn.Lineair(512,10)
]
```

nn.Flatten flatten the tensor to a vector or a 1d tensor
This is a **Linear Layer** (also called a [[Fully Connected or Dense layer]]). This is where the actual learning happen.
- **`input_size`:** This means the layer has 784 input plug one for every single unrolled pixel value from your image.
- **`512`:** This is the number of neurons inside this specific hidden layer.

this function does a lot of simple mathematical linear equation a thousand of times by its weight and biase, this is where the math happens for now i don't really understand this :p 

nn.Relu is the activation layer and corrects some values (eliminate negatives in this case)

the hidden layer (nn.Linear(512,512)) is called hidden because it isnt directly conencted to the actual image values its an extra layer of learning, where we have 512 neurones connected to 512 neurones (512x512 connections)

nn.Lineair(512,10) is the output layer, the final output is a vector fromed of 10 coordinates or 10 nodes because we have 10 possible outcomes (0,1,...,9)

```
model = nn.Sequential(\*layers)
```
A [Sequential](https://www.google.com/url?q=https%3A%2F%2Fpytorch.org%2Fdocs%2Fstable%2Fgenerated%2Ftorch.nn.Sequential.html) model expects a sequence of arguments, not a list, so we can use the [* operator](https://www.google.com/url?q=https%3A%2F%2Fdocs.python.org%2F3%2Freference%2Fexpressions.html%23expression-lists) to unpack our list of layers into a sequence.

To check which device a model is on, we can check which device the model parameters are on. Check out this [stack overflow](https://www.google.com/url?q=https%3A%2F%2Fstackoverflow.com%2Fquestions%2F58926054%2Fhow-to-get-the-device-type-of-a-pytorch-module-conveniently) post for more information.
next(model.parameters()).device

## Loss function and Optimizer

1. The model makes a prediction.
2. [[Cross Entropy Loss function|Loss function]] measures exactly the error.
3. Optimizer  is the coach who looks at that error and updates the model.

in this case we chose the [[Cross Entropy Loss function]] and the [[Adam optimizer]]

## Calculating accuracy 

```
def get_batch_accuracy(output,y,N):
  pred =output.argmax(dim=1 keepdim =True)
  correct =pred.eq(y.view_as(pred)).sum().item()
  return correct/N
```
  
output is the output vector from the model (0.1,0.55,0.36,....)
each float is how much sure is the model of that prediction 0.1 for 10% certainty of it being  0...etc
pred = output.argmax(dim=1 keepdim=True) takes the greatest value coordinate in the vector  and returns what it conveys to in this case "1", we are calculating accuracy per batch so pred would look like this \[1, 8,4,.....]last one being the 32nd. 
the second line of the code does multiple things it aligns both the prediction tensor and the correct answers tensor if the prediction equates to the correct value then its True (1) else its False(0) .sum sums all the correct prediction (32 at max 0 at min) and the .item() returns it from a tensor to a simple integer
then we return the percentage of accuracy

## Training algorithm
```
def train():
  loss =0
  accuracy =0
  
  model.train()
  for x,y in train_loader:
    x,y =x.to(device),y.to(device)
    
    output =model(x)
    optimizer.zero_grad()
    batch_loss =loss_function(output,y)
    batch_loss.backward()
    optimizer.step()
    loss+=batch_loss.item()
    accuracy += get_batch_accuracy(output,y,train_N)
  print('Train - Loss:{:.4f}Acuracy{:.4f}'.format(loss,accuracy))
 
```

First we initialized loss and accuracy to zero.

we set up the model for the training phase (training phases and evaluating phase differ from model to model)

for every tuple (x,y) inside the train_loader: x being the batch of Tensors (representing the photo of a number) and y being batch of the target (corresponding the number)  using our pre-determined device

we take the batch output of the model for each batch input 

we reinitialize the optimizer from the previous iteration

we calculate the loss for that batch using our loss function 

we go backward from the our loss to the initial weights and biases  and optimize them using our optimizer 

we sum up our loss and accuracy 


## Validating algorithm
 
```
def validate():
  loss =0
  accuracy =0
  
  model.eval()
  with torch.no_grad():
    for x,y in test_loader:
      x,y = x.to(device), y.to(device)
      
      output = model(x)
      loss +=  loss_function(output,y).item()
      accuracy += get_batch_accuracy(output,y,test_N)
    print('Valid - Loss: {:.4f} Accuracy: {:.4f}'.format(loss,accuracy))
    
```

we start by initializing the loss and accuracy 

and setting up the model to the evaluation mode 

without changing the gradient of the model for every tuple in the testing loader (using our device):

we find the output of Tensor using our model, calculate the loss and accuracy of our model