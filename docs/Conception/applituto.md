---
layout: default
title: Application Educative
parent: Conception
nav_order: 3
---

# Programmation des applications

 Dans les problématiques du projet, il nous est demandé de créer deux types d'application. La première est une application musicale et la seconde une application simple et éducative sur les fonctionnalités de la table.

Nous avons tout d'abord réfléchi à la conception de l'application qui permet de découvrir les différentes fonctionnalités de la table. Cela était plus logique pour nous car on pourrait nous aussi apprendre à manier les tags et mieux comprendre leur fonctionnement. Les premiers tests que nous avons réalisés se sont déroulés sur la table directement puisque le système pour détecter les tags était déjà opérationnel. Ces tests ont été réalisés à l'aide des 2 programmes qui se trouvent dans le dossier TUIO. Le premier nous a permis de voir la prise des informations du logiciel tel que la position en X et Y, la rotation, la vitesse... Tandis que le second programme permet de dessiner un carré au centre de l'endroit où est détecté le tag. Ce deuxième programme nous a permis de remarquer un premier problème. En effet, lorsque nous boujons un objet vers le haut ou vers le bas, le mouvement affiché par le cube était l'inverse de notre action. L'axe En ayant ces informations en tête, nous avons pu commencer à coder l'application. 

## Tutoriel

Le but de cette partie est de permettre à n'importe quel utilisateur d'apprendre à utiliser la table. La première étape logique de cet objectif, c'est de demander à l'utilisateur de placer un des objets sur l'écran. Cette étape est aussi très importante pour montrer que chaque objet est indépendant et donc n'interagit pas de la même manière avec la table.

![tuto1](images/tutuo1.gif)

Ensuite, nous pouvons passer aux différents mouvements réalisables. Les exemples que nous montrons à l'utilisateur sont, dans l'ordre, la rotation en lui demandant de tourner l'objet, la position en lui suggérant de faire un mouvement vers le haut et pour finir la vitesse grâce à un mouvement rapide.
Toutes ces actions se réalisent avec un seul et même objet, mais celles-ci sont toutes visibles grâce à un changement d'affichage.

![tuto2](images/tuto2.gif)      

Après avoir fini cette démonstration, le projecteur va afficher une fenêtre où le but sera de réaliser un puzzle avec les 5 objets de la table.

## Puzzle

Ce puzzle est comme énoncé plutôt composé de 5 objets/pièces. Le but est donc de former un carré avec toutes les formes qui vont s'afficher à l'écran en utilisant les fonctionnalités montrées précédemment. Cependant, nous n'utilisons pas la vitesse dans ce mode de l'application. Alors que la position et la rotation sont indispensables. Il faut tout de même ajouter à cela la gestion des objets entre eux car il faut un positionnement précis entre les pièces pour créer ce carré.

La première étape pour créer ce puzzle est de permettre à chaque forme de dessiner sa pièce de puzzle lorsqu'on la pose. Pour cela nous utilisons une répétition d'une multitude de fonction ` rect(x, y, w, h)` chaque lettre représentant respectivement la position en x et en y de l'angle inférieur gauche du carré voulu ainsi que par la suite sa largeur et sa hauteur. 
Ce qui donne ceci une fois terminé:

![puzzle1](images/puzzle1.png)


Cette étape doit être réalisée autant de fois que l'on veut utiliser un objet. Ici elle sera faite 5 fois pour convenir aux 5 objets. Chaque objet aura alors sa propre fonction qui sera appelée lorsque l'on positionne le tag. Ensuite, il faut pouvoir associer les pièces entre elles. C'est à ce moment qu'intervient un premier problème puisque lors de la création la fonction ` rect(x, y, w, h)`
prend comme repaire de référence le centre du tag, soit le centre de notre objet. Par conséquent, si l'on veut compléter le puzzle, la manipulation à faire est de superposer les pièces entre elles. Mais cette action n'est pas très intéressante pour l'utilisateur et n'est de toute façon pas compatible avec le fonctionnement de la table. Pour régler ce problème, il faut donc translater les coordonnées des objets pour ne pas avoir à les empiler. La direction n'a pas d'importance. Il faut juste faire attention à ce que chaque translation soit assez différente pour ne pas rencontrer le même problème qu'avec les pièces centrées. Mais aussi respecter le cadre dans lequel les tags évolués car si la translation est trop importante les pièces du puzzle seront en dehors de l'affichage du projecteur.
Voici un exemple avec 2 pièces:

![puzzle2](images/puzzle2.png)

La dernière étape consiste à vérifier si les objets sont bien positionnés pour afficher le carré complet. Ces vérifications ne se feront que lorsque les 5 objets seront placés sur la table pour plusieurs raisons. Dans un premier temps, d'un point de vue technique, si l'on vérifie à chaque fois que 2 pièces sont bien positionnées entre elles, il faudrait garder en mémoire cette information pour s'assurer que les 5 pièces sont bien placées sans oubli. Cela ne serait pas pratique et rajouterait beaucoup de ligne de code pour faire peu d'actions. Dans un second temps, pour éviter les coups de chance de l'utilisateur qui placerait 2 pièces ensemble aléatoirement. Sachant comment nous avons réalisé les pièces, il n'est pas difficile en théorie de réussir cette étape. Comme 4 pièces ont été translatées selon certaines coordonnées il nous suffit de faire la différence entre la pièce non translater et les autres puis de vérifier, avec une condition ` if()`, si le résultat de cette différence est assez proche de la translation.

Par exemple, prenons:
    * x1=200; y1=350;
    * x2=150; y2=350;
    * avec une translation en x de 75.

Dans ce cas de figure, la soustraction nous donne une différence de 50 en x et 0 en y. Le résultat en y est correct, cependant en x, cela ne correspond pas à la translation initiale. La condition n'est donc pas respectée. 

Biensur, pour éviter d'être trop exigeant sur la précision des placements, il faut prévoir une marge. Nous avons donc choisi de mettre une marge de +/- 5 car cela nous semblait être le parfait compromit entre précision et souplesse.
Voici le résultat final:

![puzzle3](images/puzzle3.png)