---
title: "Item harvested"
description: "Se activa del lado del servidor después de recolectar un item en un campo."
icon: "hand-holding"
---

Se activa después de que se haya recolectado un item en un campo.

```lua Event
RegisterNetEvent("drugs_creator:fields:itemHarvested", function(playerId, fieldId, itemName, itemQuantity)

end)
```

### Parámetros

| Nombre             | Tipo de dato | Descripción                             |
| ----------------- | --------- | -------------------------------------------- |
| `playerId`         | integer   | ID de servidor del jugador                                 |
| `fieldId`          | integer   | ID del campo donde se recolectó el item              |
| `itemName`         | string    | ID del item recién recolectado                              |
| `itemQuantity`     | integer   | Cantidad de item recolectada                              |

## Ejemplo

```lua
-- Un ejemplo para un sistema de xp
RegisterNetEvent("drugs_creator:fields:itemHarvested", function(playerId, fieldId, itemName, itemQuantity)
    TriggerEvent("xp_system:addXp", playerId, itemName, itemQuantity)
end)
```
