---
title: "Give keys to player ID"
description: "Da llaves de vehículo a un jugador conectado del lado servidor."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:giveVehicleKeysToPlayerId(playerId, plate, type)
```

### Parámetros

| Nombre       | Tipo de dato         | Descripción                                                                                                  |
| ---------- | ------------------ | ------------------------------------------------------------------------------------------------------------- |
| `playerId` | integer             | El ID de servidor del jugador objetivo                                                                                     |
| `plate`    | string              | La placa del vehículo                                                                                               |
| `type`     | string (optional)  | El tipo de vehículo. Por defecto `"temporary"`. Tipos disponibles: `"temporary"`, `"owned"`, `"other_player"`          |

## Ejemplo

```lua
RegisterNetEvent("vehicle_shop:playerBoughtVehicle", function(playerId, plate)
    exports["vehicles_keys"]:giveVehicleKeysToPlayerId(playerId, plate, "owned")
end)
```
