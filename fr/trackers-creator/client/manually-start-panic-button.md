---
title: "Démarrer manuellement le bouton panique"
description: "Déclenche le bouton panique depuis ton propre code, sans nécessiter le raccourci clavier."
icon: "hand-pointer"
---

Tu peux utiliser cet event pour démarrer manuellement le bouton panique, sans obliger le joueur à appuyer sur le raccourci clavier — par exemple, depuis un menu radial.

<Note>
  Le raccourci clavier du bouton panique peut être désactivé dans les paramètres du menu.
</Note>

```lua Event
TriggerServerEvent("trackers_creator:panicButtonPressed")
```
