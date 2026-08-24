---
title: "Comment utiliser des images pour les items"
description: "Configure des images d'items personnalisées affichées dans l'interface de la boutique."
icon: "image"
---

## Méthode globale

Le script te permet d'utiliser les images que tu veux pour les items, associées à leur nom — donc si un item s'appelle `bread`, l'image doit s'appeler `bread.png`.

Tu peux placer les images que tu veux dans le dossier `shops_creator/html/images/`.

## Je veux récupérer les fichiers d'image depuis un inventaire

Pour personnaliser le chemin par défaut où le script cherche les images, ouvre le fichier `shops_creator/integrations/cl_integrations.lua` et modifie la variable `IMAGES_PATH` avec ce que tu veux.
