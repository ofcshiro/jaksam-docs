---
title: "Remove keys from player ID"
description: "Retire des clés de véhicule à un joueur connecté côté serveur."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:removeKeysFromPlayerId(playerId, plate)
```

### Paramètres

| Nom       | Type de donnée | Description                   |
| ---------- | --------- | ---------------------------------- |
| `playerId` | integer   | L'ID serveur du joueur cible           |
| `plate`    | string    | La plaque du véhicule                      |

## Exemple

```lua
RegisterNetEvent("garage:vehicleDeleted", function(playerId, plate)
    exports["vehicles_keys"]:removeKeysFromPlayerId(playerId, plate)
end)
```
