---
tags:
  - AI/Deep_Learning
  - Analytical_Math
  - Youtube_Videos
  - course
Date /Time: "{date} {time}"
title: 3Blue1Brown what is convulsion video notes
---
# Discrete convolution
discrete convulsion is:$$ (a*b)_n=\sum_{\substack{i, j \\ i+j=n}} a_i.b_j$$example $[1,2,3,4]*[5,6,7,8] =[1\cdot5,1\cdot6+2\cdot5,1\cdot7+2\cdot6+3\cdot5,1\cdot8+2\cdot7+3\cdot6+4\cdot5,...]$
it is used in probability, image processing, differential equations. it is also used to 
its looks like the same as multiplying to polynomials $P.Q$

$(a*b)_n$ is the convolution of $(a_i)$ and $(b_i)$

in image processing we can convolute an image by a kernel meaning using a pre determined matrix (3\*3 or whatever we wanting based on the objective) to process an image 

an image is just a matrix where each color of a pixel is a vector the have 3 values for RGB or any x number of values representing the proprieties of the pixel (hue, saturation, luminescence...etc.) watch [3Blue1Brown video](https://www.youtube.com/watch?v=KuXjwB4LzSA) its a better visualization 