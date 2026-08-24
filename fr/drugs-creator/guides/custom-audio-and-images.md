---
title: "Comment ajouter de l'audio et des images personnalisés aux effets"
description: "Ajoute ta propre musique ou tes propres images aux effets des drogues en déposant des fichiers dans le bon dossier."
icon: "photo-film"
---

<Tip>
  Tu veux ajouter ta propre musique ou tes propres images aux effets des drogues ? Il te suffit de déposer des fichiers dans le bon dossier.
</Tip>

Le script scanne automatiquement les dossiers d'assets et affiche tous les fichiers valides dans le menu déroulant de l'éditeur d'effets. Aucune modification de code n'est nécessaire.

## Ajouter des fichiers audio personnalisés

<Steps>
  <Step title="Va dans le dossier audio">
    Ouvre les fichiers de ton serveur et va dans `drugs_creator/html/assets/audio/`.
  </Step>
  <Step title="Ajoute tes fichiers">
    Place tes fichiers audio dans ce dossier.
  </Step>
  <Step title="Redémarre">
    Redémarre le script ou le serveur.
  </Step>
</Steps>

Et voilà ! Les nouveaux fichiers audio apparaîtront désormais dans le menu déroulant de l'effet **Music** lors de l'édition des effets des drogues.

### Formats audio pris en charge

`mp3`, `ogg`, `wav`, `flac`, `aac`, `m4a`

## Ajouter des images personnalisées

<Steps>
  <Step title="Va dans le dossier des images">
    Ouvre les fichiers de ton serveur et va dans `drugs_creator/html/assets/img/`.
  </Step>
  <Step title="Ajoute tes fichiers">
    Place tes fichiers image dans ce dossier.
  </Step>
  <Step title="Redémarre">
    Redémarre le script ou le serveur.
  </Step>
</Steps>

Les nouvelles images apparaîtront dans les menus déroulants des effets **Trip Screen Image** et **3D World Image**.

### Formats d'image pris en charge

`jpg`, `jpeg`, `png`, `gif`, `webp`

## Remarques importantes

- Les noms de fichiers sont utilisés directement comme libellés dans le menu déroulant, donc utilise des noms descriptifs (par exemple `space_trip.jpg` plutôt que `img1.jpg`)
- Si tu ajoutes des fichiers pendant que le serveur tourne, redémarre le script pour que les changements apparaissent
- Garde des tailles de fichiers raisonnables — des images ou fichiers audio volumineux peuvent affecter les temps de chargement des joueurs
