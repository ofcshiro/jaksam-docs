---
title: "Refresh player owned vehicles"
description: "Actualiza la lista de vehículos propios de un jugador del lado servidor, por ejemplo después de una compra."
icon: "rotate"
---

Usar este export (desde el lado servidor) actualizará la lista de vehículos propios del jugador (desde `owned_vehicles` en ESX o `player_vehicles` en QBCore).

```lua Export
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(playerId, instantly)
```

### Parámetros

| Nombre        | Tipo de dato | Descripción                                                                                                                    |
| ----------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `playerId`  | integer   | El ID de servidor del jugador                                                                                                                  |
| `instantly` | boolean   | Opcional. Por defecto, espera 2 segundos antes de actualizar. Si sabes con certeza que lo necesitas al instante, pasa `true`, de lo contrario puede omitirse. |

### Ejemplo

```lua
RegisterNetEvent("vehicle_shop:playerBoughtVehicle", function(playerId, plate)
    -- Esto actualizará los vehículos propios del jugador después de comprar un vehículo (solo un ejemplo)

    exports["vehicles_keys"]:refreshPlayerOwnedVehicles(playerId)
end)
```
