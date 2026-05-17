---
tags:
  - AI/Deep_Learning
  - torch
Date /Time: "{date} {time}"
title:
---

Cross Entropy Loss function is a function that calculate the loss of a given  output from the model and the correct value. The smaller the loss the more accurate the model is

$$L = -\sum_{c=1}^{M} y_{c} \log(p_{c})$$

where $p_c$ is the prediction for each coordinate and $y_c$ is the correct value for each coordinate
For a **Classification** problem like MNIST, you aren't predicting a continuous measurement. You are dealing with probabilities that strictly live between $0.0$ and $1.0$.
Because probabilities are capped at $1.0$, the squared difference formula doesn't punish bad guesses harshly enough [[Mean Squared Error]]. Instead, Cross-Entropy swaps out the exponent for a $\log$.