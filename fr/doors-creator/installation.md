---
title: "Installation"
description: "Installe Doors Creator sur ton serveur FiveM."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- Le [script de crochetage](https://github.com/baguscodestudio/lockpick) par [baguscodestudio](https://github.com/baguscodestudio/lockpick)
- Un item `doors_lockpick` ajouté à ton système d'inventaire

<Danger>
  N'utilise **PAS** FileZilla pour uploader les fichiers, sinon le script ne fonctionnera **PAS**.

  Utilise [WinSCP](https://winscp.net/eng/download.php) à la place.
</Danger>

<Steps>
  <Step title="Télécharger et extraire">
    Télécharge le script et extrais-le dans tes resources.
  </Step>
  <Step title="Ajouter au démarrage automatique">
    Ajoute le script à ton démarrage automatique (exemple : `server.cfg`).
  </Step>
  <Step title="Configuration de la base de données">
    Le script configure **automatiquement** la base de données. Si ce n'est pas le cas, tu peux exécuter manuellement les fichiers du dossier `doors_creator/sql/`.
  </Step>
  <Step title="Script de crochetage">
    Télécharge et démarre le [script de crochetage](https://github.com/baguscodestudio/lockpick) _(crédits à [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
  </Step>
  <Step title="Ajouter l'item de crochetage">
    Ajoute l'item `doors_lockpick` à ta liste d'items, comme pour n'importe quel script.
  </Step>
  <Step title="Configurer le script">
    Configure le script depuis le menu admin in-game `/doorscreator`.
  </Step>
</Steps>

Tu es prêt ! Profite bien du script 😁

## Vérification

Ouvre `/doorscreator` en jeu. Si le menu admin s'ouvre, le script fonctionne correctement.

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux optionnellement retirer les fichiers SQL de `doors_creator/sql/`, pour que le script n'essaie pas de la configurer à nouveau à chaque démarrage.
</Note>
