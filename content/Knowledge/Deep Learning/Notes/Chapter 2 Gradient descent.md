---
tags:
  - 3Blue1Brown
  - AI/Deep_Learning
  - course
  - Neural_Network
  - Youtube_Videos
Date /Time: "{date} {time}"
title: " Chapter 2"
---
this video is about training a neural network 

we start by initialize the weights and biases to random values and we add a cost function a way to tell the neural network a way to differentiate between utter nonscience and what we have true and having in the end a numerical value that shows how well we got to the wanted value

one way is to add up the squares of the differences between each of those predictions and the correct values, this final value is the $cost$

the $cost$ is small when the network classifies the image correctly and else else wise
and then take the average $cost$ of all the training data being run through the model

cost function takes the parameters $W$ and the biases $b$ and returns $cost$ and its defined based on the network behavior on all the training data (60k images). 

our goal is to find the least input 

assuming the function has only one input to find a local minimum we could figure out the slope of a the function on that input value and "shift to the left" if the slope is positive meaning making the input value smaller and shifting to the left if the slope is negative meaning making the input value bigger. We also would make the value we add to the input proportional to the slope value so that we don't overshoot out minimum.
[interactive lesson](https://www.3blue1brown.com/?topic=neural-networks)
Problem by sheer luck we could be in a local maximum and the slope would be zero which would give us a false positive
this method only finds a local minimum

### Adding more dimensions!!

our cost function takes in place thousands of variables not just one so we cant calculate the slope however we can do something else

[[the Gradient of a function]] gives the direction of steepest increase so -Gradient gives the direction of steepest decrease 

the algorithm for computing this gradient is called [[Backpropagation]]
Gradient descent is a way to converge to a local minimum of a function

its a tightly constraint  model 
giving it a random noise that resembles not a single number will confidentially gives out a number

this is old technology called [[Multilayer perceptron]]
 because of 