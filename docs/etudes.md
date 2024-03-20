---
layout: default
nav_order: 4
title: Études et choix techniques
---

# Études et choix techniques

## Raspberry Pi

Une des problématiques du projet est de limiter les interactions avec l'extérieur et l'intérieur de la table, c'est-à-dire qu'il faut que la table soit besoin du minimum de périphériques rajoutés à son bon fonctionnement. Il est donc nécessaire que la table est ses propres outils pour fonctionner. La première étape est donc de choisir sur quel ordinateur nous allions utiliser pour faire tourner nos différentes applications. Nous avons alors choisi de partir sur une raspberry Pi 5 pour le coeur de notre système.Les motivations de ce choix sont la très petite taille de celle-ci ainsi que la facilité pour d'installation de Processing sur une raspberry. Nous pouvons ensuite brancher ce dont nous avions besoin tels qu'une souris, un clavier, un écran, des enceintes mais aussi notre projecteur et notre caméra pour détecter nos objets.

![Rasberry Pi 5](images/Raspberry.jpg)

Pour aller avec notre raspberry Pi 5, il était nécessaire d'avoir un système de refroidissement adapter car étant donné qu'il y aura plusieurs logiciels actifs en même temps il pourrait y avoir une surchauffe et donc endommager la raspberry.

![refroidisseur Raspberry](images/refroidisseur_raspberry.jpg)

## Installer processing

Une fois le raspberry Pi 5 installé, la première étape était d'installer processing.
[Processing.org](https://processing.org/download).
Téléchargé la version adéquat. Pour notre projet c'est en 64 bits.

Pour extraire le fichier ".tgz" :
```bash
$ tar -xzvf processing-4.3-linux-arm64.tgz
```

Une fois ceci fait, tapez cette commande pour excécuter processing dans le fichier ou vous l'avez extrait :
```bash
$ ./processing
```

## Installer un serveur VNC

Pour faire cela, tapez la commande suivante :
```bash
$ sudo apt-get install tightvncserver
```

Et pour lancé le server :
```bash
$ tightvncserver
```

## Installer le framework reacTIVision

Cette partie était dificile car cela n'a pas fonctionné dès le premier essai de l'installation. Des erreurs sont apparus concernant des librairies manquantes.

Dans un premier temps nous avons installé 'make' :
```bash
$ sudo apt-get install make
```

Nous avons ensuite fait un clone du projet depuis github :
```bash
$ git clone https://github.com/mkalten/reacTIVision.git
```

Installation des fonts manquantes :
```bash
$ sudo apt-get install xfonts-base
```

Recherche des librairies manquantes :
```bash
$ apt search libdc1394
Sorting... Done
Full Text Search... Done
libdc1394-25/stable,now 2.2.6-4 arm64
 high level programming interface for IEEE 1394 digital cameras

libdc1394-dev/stable,now 2.2.6-4 arm64
 high level programming interface for IEEE 1394 digital cameras - development

libdc1394-doc/stable,now 2.2.6-4 all
 high level programming interface for IEEE 1394 digital cameras - documentation

libdc1394-utils/stable,now 2.2.6-4 arm64
 utilities for IEEE 1394 digital cameras
```

Installez toutes ces librairies. Ensuite il faut installer la SDL2 :
```bash
$ sudo apt-get install libsdl2-dev
```

Puis une autre :
```bash
$ sudo apt-get install libturbojpeg0-dev
```

## Processing/Reactivision

