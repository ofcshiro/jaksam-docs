---
title: "Installation"
description: "Installe Blips Creator sur ton serveur FiveM."
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
    Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `blips_creator/sql/`.
  </Step>
  <Step title="Configure les options">
    Configure les options dans les fichiers de config (lis bien les commentaires, ils expliquent tout).
  </Step>
  <Step title="Ouvre le menu">
    Pour ouvrir le menu, appuie sur `ESPACE` sur la grande carte en jeu.
  </Step>
</Steps>

Tu es prêt ! Profite bien du script 😁

## Vérification

Appuie sur `ESPACE` sur la grande carte en jeu. Si le menu des blips s'ouvre, le script fonctionne correctement.

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux éventuellement supprimer les fichiers SQL de `blips_creator/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
</Note>
