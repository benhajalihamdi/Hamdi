---
tags:
Date /Time: "{date} {time}"
title:
---
The network gets its name because its structural diagram looks exactly like the letter **U** (Ronneberger et al., 2015). It is fundamentally an **Encoder-Decoder** network divided into two symmetrical halves connected by "skip connections" (Lu et al., 2022). 

U nets are used for:
sup resolution: upscaling the resolution of an image 
segmenting images 
diffusion models to turn gaussian noise into new generated images 

it takes as it input an image and returns a prediction in form of a different image, then calculating the loss and reoptimizing for the next batch

# the encoder
works like a traditional CNN where it takes the input image and applies a 3x3 convolutions followed by pooling layers. this decreases the dimensions and increases the number  the channel:
PS, channels are like proprieties of the image that the model tweaks and finds
# the decoder 
this uses transposed convolutions (up sampling) to systematically increase the dimensions and decrease the number of the channels


If you only down sampled an image and then up sampled it, the final output would be incredibly blurry. Why? Because pooling layers discard precise spatial details.