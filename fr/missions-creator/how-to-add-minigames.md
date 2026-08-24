---
title: "Comment ajouter des minijeux"
description: "Ajoute ton propre minijeu personnalisé à Missions Creator."
icon: "gamepad"
---

Ajouter de nouveaux minijeux est simple. Suis cette procédure pour ajouter un nouveau minijeu :

<Steps>
  <Step title="Duplique le fichier d'exemple">
    Duplique le fichier `missions_creator/client/minigames/_EXAMPLE_MINIGAME.lua`.
  </Step>
  <Step title="Renomme le fichier">
    Renomme le fichier avec le nom de ton minijeu.
  </Step>
  <Step title="Retire les marqueurs de commentaire">
    Ouvre le nouveau fichier et retire les commentaires au début et à la fin du fichier (retire les symboles `--[[` et `--]]`).
  </Step>
  <Step title="Renomme le minijeu">
    Change `YOUR_MINIGAME_NAME` par le nom de ton minijeu.
  </Step>
  <Step title="Implémente ton minijeu">
    Modifie la fonction pour qu'elle corresponde à ton minijeu. Elle doit retourner `true` en cas de succès et `false` en cas d'échec. Tu peux voir des exemples dans `datacrack.lua`, `fingerprint.lua`, et `memory_game.lua`.
  </Step>
  <Step title="Redémarre le script">
    Sauvegarde le fichier et redémarre le script. Si tout a été fait correctement (notamment l'implémentation du minijeu lui-même), tu devrais voir ton minijeu dans la liste des minijeux du script.
  </Step>
</Steps>
