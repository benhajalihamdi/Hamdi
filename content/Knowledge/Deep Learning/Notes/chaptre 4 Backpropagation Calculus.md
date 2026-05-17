---
tags:
  - 3Blue1Brown
  - AI/Deep_Learning
  - course
  - Youtube_Videos
  - Neural_Network
Date /Time: "{date} {time}"
title: Chapter 4 Backpropagation calculus
---
For now assuming each layer is made up of one neuron the last layer neuron is $L$ and its activation is $a^{(L)}$ , logically the activation of the neuron in the layer before it is $a^{(L-1)}$ and the desire value is y 
so the cost for this simple network is 
$$C_0 =(a^{(L)}-y)^2$$ this is called the [[Mean Squared Error]] 
we know that 
$$a^{(L)} =\sigma(z^{(L)})$$ where
$z^{(L)}=\omega^{(L)}a^{(L-1)}+b^{(L)})$
1st goal finding how sensitive $C_0$ to $\omega^{(L)}$ meaning finding $\frac{\partial C_0}{\partial \omega^{(L)}}$

$$\frac{\partial C_0}{\partial \omega^{(L)}} =\frac{\partial z^{(L)}}{\partial \omega^{(L)}}\frac{a^{(L)}}{\partial z^{(L)}}\frac{\partial C_0}{\partial a^{(L)}}$$

$$\frac{\partial C_0}{\partial a^{(L)}}=2(a^{(L)}-y)$$
$$\frac{a^{(L)}}{\partial z^{(L)}} =\sigma'(z^{(L)})$$

$$\frac{\partial z^{(L)}}{\partial \omega^{(L)}}=a^{(L-1)}$$
so
$$\frac{\partial C_0}{\partial \omega^{(L)}} =a^{(L-1)}\sigma'(z^{(L)})2(a^{(L)}-y)
$$and the cost of this simple network for all of the training data is 
$$\frac{\partial C}{\partial \omega^{(L)}} =\frac{1}{n}\sum_{k=0}^{n-1}\frac{\partial C_k}{\partial \omega^{(L)}}$$
where $n$ is the amount of training data 

and this is just one component of the gradient vector which takes in account all the weights and biases in this simple network

now moving to a network that has multiple neurons per layer we subscript  each layer for each neuron $a_j^{(L)}$$a_k^{(L-1)}$
where
$C_0 = \sum_{j=0}^{n_l-1}(a_j^{(l)}-y_j)^2$

$$ z_j^{(l)} = \omega_{j0}^{(l)}a_0^{(l-1)}+\omega_{j1}^{(l)}a_1^{(l-1)}+\omega_{j2}^{(l)}a_2^{(l-1)}+...+\omega_{jk}^{(L)}a_k^{(l-1)}+...+b_j^{(l)}$$
and $$ a_j^{(l)}=\sigma(z_j^{(l)})$$
$$\frac{{\partial C_0}}{\partial a_k^{(L-1)}} =

\underbrace{
\sum_{j=0}^{n_L - 1}
\frac{{\partial z_j^{(L)}}}{\partial a_k^{(L-1)}}
\frac{\partial a_j^{(L)}}{{\partial z_j^{(L)}}}
\frac{{\partial C_0}}{\partial a_j^{(L)}}
}_{\text {Sum over layer L}}$$
![[summary.jpg]]