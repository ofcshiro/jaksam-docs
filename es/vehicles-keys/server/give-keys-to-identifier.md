---
title: "Give keys to identifier"
description: "Da llaves de vehículo a un identifier de jugador del lado servidor."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:giveVehicleKeysToIdentifier(identifier, plate, type)
```

### Parámetros

| Nombre         | Tipo de dato         | Descripción                                                                                                  |
| ------------ | ------------------ | ------------------------------------------------------------------------------------------------------------- |
| `identifier` | string              | El identifier/licencia del jugador objetivo                                                                            |
| `plate`      | string              | La placa del vehículo                                                                                               |
| `type`       | string (optional)  | El tipo de vehículo. Por defecto `"temporary"`. Tipos disponibles: `"temporary"`, `"owned"`, `"other_player"`          |

## Ejemplo

```lua
RegisterNetEvent("vehicle_shop:playerBoughtVehicle", function(playerId, plate)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    local identifier = xPlayer.identifier

    exports["vehicles_keys"]:giveVehicleKeysToIdentifier(identifier, plate, "owned")
end)
```
