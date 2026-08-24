---
title: "Comment modifier les minijeux"
description: "Ajoute ton propre minijeu personnalisé à Robberies Creator."
icon: "gamepad"
---

Tu peux ajouter n'importe quel minijeu — cela nécessitera un minimum de connaissances en programmation de ta part.

<Steps>
  <Step title="Crée ton fichier de minijeu">
    Ajoute ton fichier de minijeu dans `integrations/minigames` et crée ta fonction (en utilisant `datacrack.lua`, ou tout autre minijeu existant, comme exemple).
  </Step>
  <Step title="Enregistre le minijeu">
    Modifie le fichier `integrations/cl_hack_minigame.lua` pour prendre en charge ton minijeu.
  </Step>
  <Step title="Ajoute-le à l'interface">
    Modifie `html/index.js`, cherche `"datacrack"`, et ajoute ton minijeu là aussi.
  </Step>
</Steps>
