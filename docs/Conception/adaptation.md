---
layout: default
title: Adaptation sur la table
parent: Conception
nav_order: 6
---
Une fois le plateau supérieur, le raspberry branché et la programmation de nos applications terminées, nous avons fait des tests directement sur la table. Ces tests avaient pour but de vérifier le bon fonctionnement de tout notre projet. Nous avons donc découvert certains problèmes que nous avons dû résoudre.

## Taille de la fenêtre

Le premier problème rencontré se trouve au niveau de la taille de la fenêtre. Comme nous avions progammé uniquement sur nos ordinateurs la taille de la fenêtre où s'afficher notre application était adaptée selon la résolution de notre écran. Or, pour ce qui est du raspberry cette dernière est plus petite. Nous avons donc du modifié sa taille grâce à cette fonction:
```java
size(480,450);
```
Ce changement a pour conséquence la modification de plusieurs parties du code de nos applications.

## Modification du code
Ces modifications sont majoritairement liées aux coordonnées que l'on utilise puisque les nombres 480 et 450 correspondent respectivement aux dimensions de l'axe x et y. Les principaux changements se trouvent donc au niveau de la fonction pour quitter le menu mais aussi les rectangles pour créer les pièces de puzzle. Pour ce dernier point, il faut évidemment changer les coordonnées du premier point mais aussi réduire l'échelle des rectangles pour avoir le même résultat que sur le PC. Sinon, les rectangles seraient trop grands et rendraient leurs affichages illisibles pour l'utilisateur.

## Problème avec les tags
Le dernier problème, que nous avons rencontré lors de ces tests, concerne les nouveaux objets créés. Plus particulièrement les tags collés dessus. Ces tags n'étaient pas détectés par la caméra de la table alors que la caméra de nos ordinateurs le pouvait. Nous avons donc remarqué une différence entre les tags du groupe précédent et les autres. La couleur noire, qui dessinait les tags, était plus foncé. Sachant, cela nous avons collé de nouveaux tags plus foncés pour régler le problème.