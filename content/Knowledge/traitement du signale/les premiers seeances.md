---
tags:
Date /Time: "{date} {time}"
title:
draft: false
---
![[Screenshot 2026-09-21 223638.png]]


## Classification des signaux:
### Classification dimensionnelle:
- nondimensional
- bidimensional
- 3D
- 4D
- N-D par un reseau de capteurs
### Classification phénoménologique
- signaux determinists: evolution en ft de temps qui une expression mathématique ou graphique:
	- signaux périodique
	- apériodique
	- transitoire
- signaux reels: mathématiquement est réelle et elle exprime un phénomène physique
- signaux aléatoire
### Classification énergétique
on distingue entre les signaux qui possède une énergie finie et une puissance fine et énergie infinie:

$$ E = \int_{-\infty}^{+\infty}{|{x(t)}|^2dt}$$
$$P_{moy}=\lim_{T_0=+\infty}{\frac{1}{T_0}\int_{-\frac{T_0}{2}}^{\frac{T_0}{2}}{|{x(t)}|^2dt}}$$
les signaux qui possède une énergie finie ou une P moyenne nulle généralement représente des phénomène physique

### Classification morphologique/spectrale
#### Classifcation Morphologique:
- signale analogique: a amplitude et temp continue
- signale quantifié: amplitude discrete  et temps continue
- signale échantillonne: amplitude continues temp discrete
- signale numérique; amplitude discrete et temps discrete
#### Classification spectrale:
- basse fréquence
- haute fréquence
- bande étroite 
- large bande
## Les signaux usuelles


 - **Fonction Échelon d'Heaviside $u(t)$:**

$$u(t) = \begin{cases} 1 & \text{si } t > 0 \\ 0 & \text{si } t < 0 \end{cases}$$
 - **Fonction signe $sgn(t)$:**
$$\text{sgn}(t) = \begin{cases} +1 & \text{si } t > 0 \\ 0 & \text{si } t = 0 \\ -1 & \text{si } t < 0 \end{cases}$$
- **Signal Porte / Rectangulaire ($\Pi_T(t)$)** : Signal d'amplitude 1 centré en $0$ de largeur $T$.
$$\Pi_T(t) = \begin{cases} 1 & \text{si } \vert{}t\vert{} \le \frac{T}{2} \\ 0 & \text{sinon} \end{cases}$$
- **Signal Triangle ($\Lambda_T(t)$)** : Signal triangulaire centré en $0$ de base $2T$.
$$\Lambda_T(t) = \begin{cases} 1 - \frac{\vert{}t\vert{}}{T} & \text{si } \vert{}t\vert{} \le T \\ 0 & \text{sinon} \end{cases}$$
- **Sinus Cardinal ($\text{sinc}(t)$)** : Réponse fréquentielle idéale du filtre passe-bas et interpolation de Shannon.
$$\text{sinc}(t) = \frac{\sin(\pi t)}{\pi t}$$
- **[[Fonction dirac]]**
- 
$$\delta(t)=\lim_{a=0}{\frac{1}{2a}\Pi_{2a}(t)}$$
- **Peigne du dirac:
$$\text{III}_T(t) = \sum_{n=-\infty}^{+\infty} \delta(t - nT)$$