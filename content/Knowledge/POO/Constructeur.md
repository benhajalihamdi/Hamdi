---
tags:
Date /Time: "{date} {time}"
title:
draft: false
---

Le constructer est invoqué par l'objet qu'il va construit
"this" est un pointeur sur l'obkjet qu'il invoque.
A( A const & ){}

La surcharge des constructeurs repose sur la signature de leurs paramètres : le mode de passage (par valeur, par référence ou par adresse) permet au compilateur de différencier plusieurs constructeurs tout en contrôlant la performance et la gestion de la mémoire.

**1. Le passage par référence obligatoire (Constructeur de recopie)** Le lien le plus direct concerne le constructeur de recopie. Il **doit obligatoirement** recevoir son argument par référence (`const T&`). S'il acceptait un passage par valeur (`T(T autre)`), l'appel de constructeur sera du plus recopie et on a "end up" à une recopie infinie détectable par le compilateur


## Appel de constructeur par recopie:

- initiation à la déclaration par passage d'un paramètre objet à la déclaration
	- point p = 3; <=>point p(3);
- passage d'un paramètre objet par valeur à une fonction
- valeur de retour de type classe

## Les différents passages des données:

Surdéfinir un constructeur en faisant varier le mode de passage permet d'adapter la création de l'objet selon la nature de la donnée transmise :

- **Par valeur (`T(Data d)`) :** L'argument est copié. Utile pour les types primitifs (`int`, `double`) ou lorsque le constructeur modifie sa propre copie locale sans altérer l'original.
- **Par référence constante (`T(const Data& d)`) :** Évite la copie lourde d'un objet en mémoire tout en garantissant que l'original ne sera pas modifié. C'est la norme pour passer des objets complexes.
- **Par adresse/pointeur (`T(const Data* d)`) :** Permet de gérer des arguments optionnels. L'utilisateur peut passer `nullptr` si la donnée n'est pas disponible.