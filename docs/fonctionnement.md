---
layout: default
nav_order: 3
title: Fonctionnement du projet
---

# Fonctionnement de la table

Lorsqu'un tag est déposé sur la table, celui-ci est détecté par une caméra sur laquelle un filtre infra-rouge est installé. La caméra est reliée directement par l'intermédiaire d'un câble USB au raspberry pi 5. Des données sont ensuite captées (coordonnées x et y du tag, accélération...) par celle-ci et envoyées via un protocole (TUIO) vers notre application. L'application est développée sous processing en java. Une fois que notre application est reçut les données, celles-ci sont ensuite traitées pour mettre diverses actions. Cela peut-être d'afficher du texte, une image ou une forme. L'affichage est réalisé par un vidéo projecteur.