---
title: "Installation"
description: "Installe Races Creator sur ton serveur FiveM."
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
    Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `races_creator/sql/`.
  </Step>
</Steps>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] Aucune vérification in-game pour une installation réussie n'est encore documentée pour Races Creator.
</Info>

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux éventuellement supprimer les fichiers SQL de `races_creator/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
</Note>
