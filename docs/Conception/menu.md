---
layout: default
title: Menu
parent: Conception
nav_order: 5
---

# Création d'un Menu 

Afin de séparer les deux applications et de permettre à l'utilisateur de choisir celle qu'il souhaite lancer, nous devions créer un menu. 

Nous avons pour cela, continué sur notre lancée et programmé en Java sous Processing.
Nous avons simplement afficher le nom des deux applications sur la table, une en haut et l'autre en bas. 

![menu](menu1.png)

L'utilisateur n'a plus qu'à faire son choix. Il peut ainsi utiliser un objet et le déplacer en haut ou en bas pour valider son choix. 
Comme pour les autres applications, les coordonnées du tag, plus précisemment X et Y, sont récupérées et permettent l'éxecution d'une des deux applications en fonction des résulats obtenus.

Nous avons également ajouté une option dans les deux applications, permettant à l'utilisateur de revenir au menu principal à tout moment. 
Il doit simplement déplacer un tag vers la partie inférieure droite de l'écran, vers l'icône correspondante. 

![icône](menu2.png)

Pour ce faire, nous avons simplement délimiter une zone en bas de l'écran à l'aide des coordonnées. Si un tag franchit cette zone et dépasse les coordonnées nécessaires, alors l'application se ferme et laisse place au menu.

```java
if(x0*480>=440 && y0*450>=410 && tobj.getSymbolID() == 0 && etape_musique  ){
              etape_musique=false;
              backgroundColor=0;
            }
```

Comme on peut le voir dans le code si dessus, pour réaliser ce menu nous avons utilisé plusieurs ` boolean`, ici ` etape_musique`. Cela permet de naviguer facilement entre les applications. Nous avions pensé à d'autres moyens comme l'utilisation d'une boucle ` while()`. Le problème étant que tout au long de l'exécution du programme nous nous trouvons dans la fonction `draw()`. Cette fonction permet l'actualisation permanente de l'affichage du programme, donc lorsque l'on utilise une boucle ` while()`, le programme va alors se bloquer dans cette même boucle puisqu'il ne peut plus mettre à jour la position des tags par exemple.

