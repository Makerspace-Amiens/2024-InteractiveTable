---
layout: default
nav_order: 5
title: Conception et prototypage
---

# Conception et prototypage

## Programmation des applications

 Dans les problématiques du projet, il nous est demandé de créer deux types d'application. La première est une application musicale et la seconde une application simple et éducative sur les fonctionnalités de la table.

Nous avons tout d'abord réfléchi à la conception de l'application qui permet de découvrir les différentes fonctionnalités de la table. Cela était plus logique pour nous car on pourrait nous aussi apprendre à manier les tags et mieux comprendre leur fonctionnement. Les premiers tests que nous avons réalisés se sont déroulés sur la table directement puisque le système pour détecter les tags était déjà opérationnel. Ces tests ont été réalisés à l'aide des 2 programmes qui se trouvent dans le dossier TUIO. Le premier nous a permis de voir la prise des informations du logiciel tel que la position en X et Y, la rotation, la vitesse... Tandis que le second programme permet de dessiner un carré au centre de l'endroit où est détecté le tag. Ce deuxième programme nous a permis de remarquer un premier problème. En effet, lorsque nous boujons un objet vers le haut ou vers le bas, le mouvement affiché par le cube était l'inverse de notre action. L'axe En ayant ces informations en tête, nous avons pu commencer à coder l'application. 

### Tutoriel

Le but de cette partie est de permettre à n'importe quel utilisateur d'apprendre à utiliser la table. La première étape logique de cet objectif, c'est de demander à l'utilisateur de placer un des objets sur l'écran. Cette étape est aussi très importante pour montrer que chaque objet est indépendant et donc n'interagit pas de la même manière avec la table.

![tuto1](images/tuto1.jpg)

Ensuite, nous pouvons passer aux différents mouvements réalisables. Les exemples que nous montrons à l'utilisateur sont, dans l'ordre, la rotation en lui demandant de tourner l'objet, la position en lui suggérant de faire un mouvement vers le haut et pour finir la vitesse grâce à un mouvement rapide.
Toutes ces actions se réalisent avec un seul et même objet, mais celles-ci sont toutes visibles grâce à un changement d'affichage.

![tuto2](images/tuto2.jpg)      ![tuto3](images/tuto3.jpg)

Après avoir fini cette démonstration, le projecteur va afficher une fenêtre où le but sera de réaliser un puzzle avec les 5 objets de la table.

### Puzzle

