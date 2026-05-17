---
tags:
  - 3Blue1Brown
  - AI/Deep_Learning
  - course
  - Neural_Network
  - Youtube_Videos
Date /Time: "{date} {time}"
title: Chapter 3 Backpropagation, intuitively
---
the objective is to modify and alter the weights and biases of a network so that it precise and returns the prediction we are looking for.

we have the $cost$ which represents how well we got to the wanted value

assuming x is our correct value we want the prediction of x to be as near to 1 as possible while any other value to be as near to 0 as possible, prioritizing the alteration of the x prediction over a prediction for y that may already be near 0

lets take at hand only the activation of the x  neuron which is  
$$a_0^{(k+1)} = \sigma(\omega_{0,0}a_0^{(k)}+\omega_{0,1}a_1^{(k)}+\omega_{0,2}a_2^{(k)}+...+\omega_{0,m}a_m^{(k)}+b_k)$$

we could increase $b$ or increase $w_i$ or change $a_i$ entirely:
we can increase b

increasing $w_i$ that are multiplied by greatest $a_i$ has the biggest effect

also changing the $a_i$ that have the greatest $w_i$ to be bigger and changing the $a_i$ that has the smallest $w_i$ to be smaller give us the biggest effect 

"We care about which one gives u the most bang for your buck"

however we don't have access directly to those activations but we have access to the weights and biases behind them

this is reminiscent for [[Hebbian Theory]] in neuroscience

this is what x desires so its prediction is increased we also we want the other neurons to be less active 
and each neuron has its own 'desire' for the second to last layer 

the desire of this x is added together is desire of all the other output neurons for what should happen to layer behind it in proportion to the corresponding weights and in proportion to  how much neurons needs to change

here the idea of propagating backwards comes to shine by adding all these desired effects we get a list of nudges that we want to happen to the second to last layer and we can recursively apply this to the layer behind it  back propagating 

and all this is how one training example wishes to nudge each one of these weights and biases

mathematically check [[chaptre 4 Backpropagation Calculus]] 