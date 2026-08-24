---
title: "Joueur a perdu le signal"
description: "Se déclenche côté serveur quand un joueur perd le signal d'un tracker."
icon: "satellite-dish"
---

Cet event se déclenche quand un joueur perd le signal d'un tracker, parce qu'il a perdu l'item nécessaire.

```lua Event
AddEventHandler("trackers_creator:playerLostSignalWithTracker", function(playerId, trackerId)

end)
```

### Paramètres

| Nom        | Type de donnée | Description                        |
| ----------- | --------- | ------------------------------------ |
| `playerId`  | integer   | Le server ID du joueur          |
| `trackerId` | integer   | L'ID du tracker qui a perdu le signal      |

## Exemple

```lua
RegisterNetEvent("trackers_creator:playerLostSignalWithTracker", function(playerId, trackerId)
    -- Tu peux utiliser n'importe quel code ici pour récupérer des données depuis la base de données ou faire autre chose
end)
```
