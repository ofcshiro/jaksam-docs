---
title: "Give keys to player ID"
description: "Donne des clés de véhicule à un joueur connecté côté serveur."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:giveVehicleKeysToPlayerId(playerId, plate, type)
```

### Paramètres

| Nom       | Type de donnée         | Description                                                                                                  |
| ---------- | ------------------ | ------------------------------------------------------------------------------------------------------------- |
| `playerId` | integer             | L'ID serveur du joueur cible                                                                                     |
| `plate`    | string              | La plaque du véhicule                                                                                               |
| `type`     | string (optional)  | Le type de véhicule. Par défaut `"temporary"`. Types disponibles : `"temporary"`, `"owned"`, `"other_player"`          |

## Exemple

```lua
RegisterNetEvent("vehicle_shop:playerBoughtVehicle", function(playerId, plate)
    exports["vehicles_keys"]:giveVehicleKeysToPlayerId(playerId, plate, "owned")
end)
```
