---
title: "Give keys to identifier"
description: "Donne des clés de véhicule à un identifier de joueur côté serveur."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:giveVehicleKeysToIdentifier(identifier, plate, type)
```

### Paramètres

| Nom         | Type de donnée         | Description                                                                                                  |
| ------------ | ------------------ | ------------------------------------------------------------------------------------------------------------- |
| `identifier` | string              | L'identifier/la licence du joueur cible                                                                            |
| `plate`      | string              | La plaque du véhicule                                                                                               |
| `type`       | string (optional)  | Le type de véhicule. Par défaut `"temporary"`. Types disponibles : `"temporary"`, `"owned"`, `"other_player"`          |

## Exemple

```lua
RegisterNetEvent("vehicle_shop:playerBoughtVehicle", function(playerId, plate)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    local identifier = xPlayer.identifier

    exports["vehicles_keys"]:giveVehicleKeysToIdentifier(identifier, plate, "owned")
end)
```
