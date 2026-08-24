---
title: "Installation"
description: "Installe Easy Allowlist & Queue sur ton serveur FiveM."
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
    Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `easy_allowlist/sql/`.
  </Step>
  <Step title="Whiteliste-toi">
    Pour t'ajouter à l'allowlist, utilise la commande `add_allowlist REQUEST_ID` dans la console du serveur après avoir envoyé la demande.
  </Step>
  <Step title="Configure les paramètres in-game">
    Configure les paramètres in-game en suivant aussi ce guide.
  </Step>
</Steps>

Tu es prêt ! Profite bien du script 😁

## Vérification

Exécute `add_allowlist REQUEST_ID` dans la console du serveur (selon l'étape "Whiteliste-toi" ci-dessus). Si la commande est reconnue et s'exécute sans erreur de commande inconnue, le script fonctionne correctement.

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux éventuellement supprimer les fichiers SQL de `easy_allowlist/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
</Note>
