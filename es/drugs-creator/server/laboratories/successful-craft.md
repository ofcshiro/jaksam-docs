---
title: "Successful craft"
description: "Se activa del lado del servidor después de un craft exitoso en un laboratorio."
icon: "flask-round-potion"
---

Se activa después de un craft exitoso en un laboratorio.

```lua Event
RegisterNetEvent("drugs_creator:laboratory:successfulCraft", function(playerId, ingredientsUsed, itemsToGive, laboratoryId)

end)
```

### Parámetros

| Nombre                | Tipo de dato     | Descripción                                                                                                    |
| -------------------- | -------------- | -------------------------------------------------------------------------------------------------------------- |
| `playerId`            | integer         | ID de servidor del jugador                                                                                                    |
| `ingredientsUsed`     | table           | Tabla con los ingredientes usados. Key = nombre del ingrediente, Value = cantidad del ingrediente                            |
| `itemsToGive`         | table/array     | Un array de tablas que representan los items a entregar. Cada tabla tiene las propiedades `itemName` y `itemQuantity`            |
| `laboratoryId`        | integer         | ID del laboratorio                                                                                                        |

## Ejemplo

```lua
-- Un ejemplo para un sistema de xp
RegisterNetEvent("drugs_creator:laboratory:successfulCraft", function(playerId, ingredientsUsed, itemsToGive, laboratoryId)
    for k, resultItem in pairs(itemsToGive) do
        local itemName = resultItem.itemName
        local quantity = resultItem.itemQuantity

        TriggerEvent("xp_system:addXp", playerId, quantity)
    end
end)
```
