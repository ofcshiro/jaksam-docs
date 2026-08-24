---
title: "Self give vehicle plate"
description: "Donne-toi les clés d'une plaque de véhicule spécifique."
icon: "key"
---

Tu peux utiliser cet event pour te donner toi-même une plaque de véhicule, par exemple dans les events où ton framework fait apparaître un véhicule avec la commande `/car`.

```lua Event
TriggerServerEvent("vehicles_keys:selfGiveVehicleKeys", plate)
```

### Note

Si tu veux un moyen plus simple de te donner les clés du véhicule que tu conduis actuellement, consulte [cette page](/fr/vehicles-keys/client/self-give-current-vehicle-plate).
