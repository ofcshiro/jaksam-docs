---
title: "Installation"
description: "Installe Dealerships Creator sur ton serveur FiveM, incluant la génération automatique optionnelle d'images de véhicules."
icon: "download"
---

L'installation du script est extrêmement simple.

<Danger>
  N'utilise **PAS** FileZilla pour uploader les fichiers, sinon le script ne fonctionnera **PAS**.

  Utilise [WinSCP](https://winscp.net/eng/download.php) à la place.
</Danger>

<Steps>
  <Step title="Télécharge et extrais">
    Télécharge le script et extrais-le dans tes resources.
  </Step>
  <Step title="Ajoute à l'auto start">
    Ajoute le script dans ton auto start (exemple : `server.cfg`).
  </Step>
  <Step title="Configuration de la base de données">
    Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `dealerships_creator/sql/`.
  </Step>
</Steps>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] Aucune vérification in-game pour une installation réussie n'est encore documentée pour Dealerships Creator.
</Info>

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux éventuellement supprimer les fichiers SQL de `dealerships_creator/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
</Note>

## Création automatique d'images — Optionnel

Si tu veux utiliser la création automatique d'images de véhicules, suis ces étapes :

<Steps>
  <Step title="Installe screenshot-basic">
    Installe [screenshot-basic](https://github.com/citizenfx/screenshot-basic) (tu l'as probablement déjà).
  </Step>
  <Step title="Installe yarn">
    Installe [yarn](https://github.com/citizenfx/cfx-server-data) (tu l'as probablement déjà — `resources/[system]/[builders]`).
  </Step>
  <Step title="Installe webpack">
    Installe [webpack](https://github.com/citizenfx/cfx-server-data) (tu l'as probablement déjà — `resources/[system]/[builders]`).
  </Step>
  <Step title="Configure les permissions du dossier">
    Assure-toi que le dossier `dealerships_creator` et le dossier `dealerships_creator/_vehicles_images` ont les permissions de lecture/écriture (clic droit sur les dossiers → Propriétés → active les permissions de lecture (**R**) et écriture (**W**)).
  </Step>
</Steps>
