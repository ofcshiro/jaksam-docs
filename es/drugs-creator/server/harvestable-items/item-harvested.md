---
title: "Item harvested"
description: "Se activa del lado del servidor después de recolectar un item recolectable."
icon: "hand-holding"
---

Se activa después de que se haya recolectado un item recolectable.

```lua Event
RegisterNetEvent("drugs_creator:harvest:itemHarvested", function(playerId, itemName, itemQuantity)

end)
```

### Parámetros

| Nombre             | Tipo de dato | Descripción             |
| ----------------- | --------- | --------------------------- |
| `playerId`         | integer   | ID de servidor del jugador                 |
| `itemName`         | string    | ID del item recién recolectado             |
| `itemQuantity`     | integer   | Cantidad de item recolectada             |

## Ejemplo

```lua
-- Un ejemplo para un sistema de xp
RegisterNetEvent("drugs_creator:harvest:itemHarvested", function(playerId, itemName, itemQuantity)
    TriggerEvent("xp_system:addXp", playerId, itemQuantity)
end)
```
