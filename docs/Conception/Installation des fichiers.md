---
layout: default
title: Installation sur le Raspberry
parent: Conception
nav_order: 6
---

## Installer processing

Une fois le système d'exploitation installé sur le raspberry Pi 5, la première étape était d'installer processing.
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
faites attention à bien être dans le bon répertoire.

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

## Lancement de l'application avec processing

Le but est d'excécuter notre application avec `processing` au démarrage du raspberry pi 5.
Beaucoup de forum sont disponibles sur internet mais ils sont tous enciens et sont donc obsolètes pour le raspberry pi 5.

Dans un premier temps nous avons édité le fichier `wayfire.ini` avec la commande suivante :
```bash
$ sudo nano .config/wayfire.ini
```

Allez regarder la section `[autostart]` et si elle n'existe pas vous pouvez simplement la créer.
Voici pour ma part ce que le fichier contient :
```bash
$ sudo nano .config/wayfire.ini
[autostart]
panel = wfrespawn wf-panel-pi
background = wfrespawn pcmanfm --desktop --profile LXDE-pi
xdg-autostart = lxsession-xdg-autostart
chromium = chromium-browser https://raspberrypi.com https://time.is/London --kiosk --noerrdialogs --disable-infobars --no-first-run --ozone-platform=wayland >
start = /home/reactable/Documents/testJavaProcessing/sketch/linux-aarch64/sketch
screensaver = false
dpms = false
```

--`chromium` permet d'ouvrir une page chromium.
--`start` permet de lancer un script .sh

Pour plus d'information vous pouvez aller voir sur [le site](https://www.raspberrypi.com/tutorials/how-to-use-a-raspberry-pi-in-kiosk-mode/#:~:text=ini%20.%20.-,config%2Fwayfire.,desktop%20in%20Raspberry%20Pi%20OS.&text=This%20line%20opens%20the%20Chromium,.com%20and%20time.is%20.)