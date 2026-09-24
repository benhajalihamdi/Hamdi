---
tags:
Date /Time: "{date} {time}"
title:
draft: false
---
## Definitions

 - soit $f$ est continue sur $[a,b[$ avec $a<b$ où $a\in R,a\in R\cup\{-\infty\}$   
l'intégrale $\int_b^a{f(x)dx}$ *converge*  si $\lim_{x \to b^- ou -\infty} \int_x^a{f(t)dt} \in R$
de meme pour $a$ dans l'autre direction.

- soit $f$ est maintenant continue en $]a,b[$ et $a \in R\cup\{+\infty\}$ et $b\in R\cup\{-\infty\}$
donc pour que l'integrale *converge* il suffit que il existe un $c$ tel que
$\lim_{x \to b^- ou -\infty} \int_x^c{f(t)dt} \in R$ et $\lim_{x \to a^+ ou +\infty} \int_c^x{f(t)dt} \in R$
**dans le cas contraire elle ne converge plus**

Remarque:(brought u by Gemini)
Yes, improper Riemann integrals of the form $\int_1^\infty \frac{1}{x^p} \, dx$ follow the exact same convergence criteria as Riemann $p$-series ($\sum_{n=1}^\infty \frac{1}{n^p}$): **both converge if and only if $p > 1$**, and **both diverge if $p \le 1$** 

Q: est ce que le nature des series des fts f(t) et des integrales f(t) a plus infinie est la meme?

## I intégrale du Riemann

$\int_1^{\infty}{\frac{1}{t^{\alpha}}dt}$ converge ssi  $\alpha > 1$  (le problem a l'infinie)
$\int_0^{1}{\frac{1}{t^{\alpha}}dt}$ converge ssi  $\alpha <1$   (le problem en 0)

## II Critière du convergence

On considère que les fonction étudié sont du signe constant, et précisément pour la faciliter de signe positive. Et en prend I un intervalle.

- Critière du comparison:
soient f et g deux fts continues et de signe positive sur I
on suppose que f<=g sur I

Si $\int_{a}^b{g(t)dt}$ converge alors $\int_{a}^b{f(t)dt}$ converge

- Corollaire:
soient f et g deux fts continues et de signe positive sur I telles que $f =_{(b)} O(g)$ 

Si $\int_{a}^b{g(t)dt}$ converge alors $\int_{a}^b{f(t)dt}$ converge

=> c'est un corollaire du critière qui détermine que cette comparison se fait à partir d'un certain rang


## III Propriétés des intégrales généralisées 
Dans la suite, on considèrera 𝐼 =(𝑎,𝑏) un intervalle de ℝ ouvert ou semi-ouvert et 𝑓,𝑔 :𝐼 →ℝ deux fonctions continues par morceaux. Les propriétés usuelles suivantes sont vérifiées :

- positivité : si ∫𝐼𝑓 converge et si 𝑓 ≥0 sur 𝐼, alors ∫𝐼𝑓 ≥0 ;
(remaraque: si  ∫𝐼𝑓 diverge et si f>=0 sur I alors p ∫𝐼𝑓 tend vers +infinie (a demontrer) )
- linéarité : si ∫𝐼𝑓 et ∫𝐼𝑔 convergent, alors pour tout 𝜆 ∈𝕂, ∫𝐼(𝑓 +𝜆⁢𝑔) converge et ∫𝐼(𝑓 +𝜆⁢𝑔) =∫𝐼𝑓 +𝜆⁢∫𝐼𝑔.
- relation de Chasles : si ∫𝐼𝑓 converge, alors pour tout 𝑐 ∈$]a,b[$ ∫𝑐𝑎𝑓 et ∫𝑏𝑐𝑓 convergent et on a ∫𝑏𝑎𝑓=∫𝑐𝑎𝑓+∫𝑏𝑐𝑓.
## Théorème (intégration par parties) :

Soient $f,g : ]a,b[ \to \mathbb{R}$ deux fonctions de classe $\mathcal{C}^1$ telles que $\lim_{t \to a} f(t)g(t)$ et $\lim_{t \to b} f(t)g(t)$ existent. Alors les intégrales $\int_a^b f(t)g'(t) \, \mathrm{d}t$ et $\int_a^b f'(t)g(t) \, \mathrm{d}t$ sont de même nature.

Lorsqu'elles sont convergentes, on a :
$$
\int_a^b f'(t)g(t) \, \mathrm{d}t = f(b)g(b) - f(a)g(a) - \int_a^b f(t)g'(t) \, \mathrm{d}t
$$