---
title: "Remove keys from identifier"
description: "Retire des clés de véhicule à un identifier de joueur côté serveur."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:removeKeysFromIdentifier(identifier, plate)
```

### Paramètres

| Nom         | Type de donnée | Description                     |
| ------------ | --------- | ----------------------------------- |
| `identifier` | string    | L'identifier du joueur cible           |
| `plate`      | string    | La plaque du véhicule                       |

## Exemple

```lua
RegisterNetEvent("garage:vehicleDeleted", function(playerId, plate)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    local identifier = xPlayer.identifier

    exports["vehicles_keys"]:removeKeysFromIdentifier(identifier, plate)
end)
```
