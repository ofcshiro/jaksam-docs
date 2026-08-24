---
title: "Installation"
description: "Installe Shops Creator sur ton serveur FiveM."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- Le [script de coffre-fort](https://github.com/VHall1/pd-safe) de [VHall1](https://github.com/VHall1) (si tu veux la fonctionnalité de crochetage de coffres-forts)

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
    Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `shops_creator/sql/`.
  </Step>
  <Step title="Script de coffre-fort">
    Télécharge et démarre le [script de coffre-fort](https://github.com/VHall1/pd-safe) _(crédits à [VHall1](https://github.com/VHall1))_.
  </Step>
</Steps>

Tu es prêt ! Profite bien du script 😁

## Vérification

Ouvre `/shopscreator` en jeu. Si le menu s'ouvre, le script fonctionne correctement.

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux éventuellement supprimer les fichiers SQL de `shops_creator/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
</Note>
