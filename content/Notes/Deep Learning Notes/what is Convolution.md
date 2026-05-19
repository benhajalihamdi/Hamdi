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

Computationally its take more time to do a convolution of two arrays than to multiply them. Simple direct convolve functions have a complexity $O(n^2)$

multiplying two polynomials $P,Q$ is the same as convoluting their coefficients.


this gives us a different way to compute a convolution  of two series $(a_i)$ and $(b_i)$:
- multiplying  $P(x) = \sum_{i=0}^{n} a_i x^i$ and $Q(x) = \sum_{i=0}^{n} b_i x^i$ for $n$ distinct $x$  (finding $n$ samples)
- finding the coefficients $c_i$ of $(P\cdot Q)(x)$ using a system containing $n$ equations


this seems more complex because finding the $n$ samples is already complex enough and solving the system would add to the complexity. However we would use  [[FFT algorithm]]. and use Fourier transforms instead of using an arbitrary distinct $x$  as the input for each sample we would use:

$$\omega\space for\space \omega^n =1 \to \omega=e^{\frac{2\pi i}{n}}$$

this would give us a redundant variables in the calculations because $\omega^{n+k} =\omega^k\space for\space k<n$

so our process to find the convolution  of two series $(a_i)$ and $(b_i)$ would more look like:
- find the Fourier transforms of both series respectfully $(\hat{a_i})$ and $(\hat{b_i})$ using FFT
- multiply for each point ( finding $(\hat{a_i}\hat{b_i})$) 
- finding the coefficient of the resulting polynomial using inverse FFT

further potential notes on  [[Discrete Fourier transform]], [[Fast  Fourier transform]]