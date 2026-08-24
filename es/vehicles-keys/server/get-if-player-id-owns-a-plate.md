---
title: "Get if player ID owns a plate"
description: "Comprueba si un jugador específico es dueño de una placa de vehículo del lado servidor."
icon: "circle-question"
---

Este export se puede usar para saber si un jugador es dueño de una placa de vehículo (también puede comprobar compartidas, temporales, etc.).

```lua Export
exports["vehicles_keys"]:isPlayerOwnerOfVehiclePlate(playerId, plate, onlyOwnedVehicles)
```

### Parámetros

| Nombre                 | Tipo de dato | Descripción                                                                                     |
| --------------------- | --------- | ---------------------------------------------------------------------------------------------------- |
| `playerId`             | integer   | El ID de servidor del jugador                                                                                   |
| `plate`                | string    | La placa del vehículo a comprobar                                                                              |
| `onlyOwnedVehicles`    | boolean   | `true` = buscar solo en vehículos propios. `false` = buscar también en vehículos temporales, llaves compartidas, etc.         |

### Valor de retorno

`true` si el vehículo es propio.

`false` si el vehículo no es propio.

## Ejemplo

```lua
RegisterCommand("checkPlate", function(playerId, args)
    local plate = args[1] -- Ejemplo "ABC 123"

    if(exports["vehicles_keys"]:isPlayerOwnerOfVehiclePlate(playerId, plate, false)) then
        print("I own this vehicle plate")
    else
        print("I DO NOT own this vehicle plate")
    end
end)
```
