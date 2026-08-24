---
title: "Self remove vehicle plate"
description: "Retire tes propres clés pour une plaque de véhicule spécifique."
icon: "key"
---

Tu peux utiliser cet event pour te retirer toi-même une plaque de véhicule, par exemple dans les events où ton framework supprime un véhicule avec la commande `/dv`.

```lua Event
TriggerServerEvent("vehicles_keys:selfRemoveKeys", plate)
```
