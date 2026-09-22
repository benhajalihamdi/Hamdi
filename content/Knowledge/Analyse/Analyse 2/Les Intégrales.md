---
tags:
Date /Time: "{date} {time}"
title:
draft: false
---
l'integrales a evolue au cours de temps et on a étudié plusiur définitions

# Somme du Riemann

$$\int_a^b f(x) \, dx = \lim_{n \to \infty} \sum_{i=1}^n f(x_i) \Delta x$$

# L'intégrale Indéfinis ou Antidérivée 

L'intégrale Indéfinis ou Antidérivée du $f(x)$ noté $\int{f(x)dx}$ c'est à dire la primitive d'une fonction.
$$\int{f(x)dx}=F(x)+C$$
où $F(x)$ est la fonction définie par $F'(x)=f(x)$ est $C$ une constante.

# Intégrale définie

les mathématiciens ont ajouter à cette définition.
si $f$ une fonction continue sur  $[a,b]$  avec $a<=b$ et $a,b \in R ,$ 
alors f admet un intégrale $\int_a^b{f(x)dx}$ qui représente l'aire du la partie séparée par le courbe $C_f$ et l'axe des abscisses dans l'intérvale  $[a,b]$


## Formule de changement de variable
C'est possible de calculer $\int{f(x)dx}$ en remplaçant $x$ par $g(u)$ et $dx$ par $g'(u)du$ (voir [[La Dérivabilité]]) 
$$\int{f(x)dx} = \int{f(g(u))g'(u)du}$$

### Particulierité pour changement du variables:

1. Pour $\int{sin^m xcos^n xdx}$ : si $m$ est impair, on pose $u = cosx$ . Si $n$ est impair, on pose $u = sinx$.
2.  Pour $\int{\frac{tan^m x}{cos^n xdx}}$ : si $m$ est pair, on pose $u = tanx$ . Si $n$ est impair, on pose $u = secx = \frac{1}{cosx}$.

## Intégration par partie
Si $u$ et $v$ sont deux fonction $dérivables$ de $x$.
$$d(uv) = u.dv+v.du$$$$u.dv = d(uv) -v.du$$ $$\int{udv} =uv - \int{vdu}$$
## Intégrales par fractions partielles:

Remarque: les fractions partielles ce sont les fractions qui en haut on a un polynôme de degré n et en bas un polynôme de degré n+1.

En algèbre on peut simplifier les fractions partielles a une somme des fractions ou en haut on a une constante et en bas on a un polynôme (voir [[Fractions Partielles]])

