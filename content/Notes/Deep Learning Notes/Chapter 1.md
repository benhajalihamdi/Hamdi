---
tags:
  - AI/Deep_Learning
  - Neural_Network
Date /Time: "{date} {time}"
title: Chapter 1
draft: false
---
Why is it reasonable to expect the neural layered structure to behave intelligently?
a nine is formed by a loop up top and a line at the bottom...etc.

in a perfect world we want a neuron at the very to last layer in the network to "detect" or "set off" the loop up top shape, In a way that any Number having a loop at the top fires off that neuron (8 or 9)

we can divide that loop into small parts and which we hope that they are being fired in  the layer before it 

--Does the network actually behave like this?

this abstraction can also work for other examples ( speech, image recognition...etc.)

what parameter should exist so it is expressive enough to capture any pattern in a this given model (recognizing number from $0$ to $9$)

we assign a weight for every connection between the neurons from layer n to a neuron in layer $n+1$ and take each activation (value of a neuron in layer $n$) to compute their weighted sum according to their weights

$$b_0=\omega_0 a_0+\omega_1 a_1 +...+ \omega_m a_m$$
$m$ being the number of neurons in layer $k$
$b_0$ being the value of first neuron in layer $k+1$ 
$a_i$ being the values of neurons in layer $k$
$w_i$ value value of weights

this function gives us any value but we want the activation to be some value between 0 and 1, we could pump this weighted sum into a common function that returns in $]0,1[$ .
example: the [[Sigmoid Function]] or logistic curve 
$$\sigma(x)=\frac{1}{1+e^{-x}}$$
the bias is how high the weighted sum needs to be before the neurons are being meaningfully active  

Final function 
 
$$ a_0^{(k+1)} = \sigma(\omega_{0,0}a_0^{(k)}+\omega_{0,1}a_1^{(k)}+\omega_{0,2}a_2^{(k)}+...+\omega_{0,m}a_m^{(k)}+b_k)$$ OR

$$
a_0^{(1)}=\sigma(\begin{bmatrix}
\omega_{0,0}&\omega_{0,1}&...&\omega_{0,m}
\end{bmatrix}
\begin{bmatrix}
a_0^{(k)}\\
a_1^{(k)}\\
...\\
a_m^{(k)}
\end{bmatrix}+b_0)
$$

now for every neuron in layer $k+1$

$$
\begin{bmatrix}
a_0^{(k+1)}&a_1^{(k+1)}&...&a_n^{(k+1)}
\end{bmatrix}=\sigma(\begin{bmatrix}
\omega_{0,0}&\omega_{0,1}&...&\omega_{0,m}\\
\omega_{1,0}&\omega_{1,1}&...&\omega_{1,m}\\
...&...&...&...\\
\omega_{n,0}&\omega_{n,1}&...&\omega_{n,m}
\end{bmatrix}
\begin{bmatrix}
a_0^{(k)}\\
a_1^{(k)}\\
...\\
a_m^{(k)}
\end{bmatrix}+
\begin{bmatrix}
b_0\\
b_1\\
...\\
b_m
\end{bmatrix})
$$


$$\iff$$ 

$$a^{(1)} =\sigma(Wa^{(0)}+b)$$

$m$ is the number of neurons in layer $k$ and $n$ is the number of neurons in layer $k+1$

final remarques: a neuron is more a function that takes in all of the previous neurons responses and give out a number 

a network is also just a function