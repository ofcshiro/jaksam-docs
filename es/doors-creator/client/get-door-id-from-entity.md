---
title: "Get door ID from entity"
description: "Resuelve un ID de puerta a partir de su handle de entidad."
icon: "magnifying-glass"
---

```lua Export
exports["doors_creator"]:getDoorIdFromEntity(entity)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                                  |
| -------- | --------- | ----------------------------------------------- |
| `entity` | integer   | El handle de la entidad del que obtener el ID de puerta        |

### Valor de retorno

| Tipo de dato | Descripción                            |
| --------- | ----------------------------------------- |
| integer   | El ID de la puerta si se encuentra, `nil` en caso contrario      |

## Ejemplo

```lua
-- Este ejemplo muestra cómo añadir una opción de target para comprobar los IDs de puerta usando ox_target
-- Nota: esto es solo un ejemplo, tendrás que adaptarlo a tus necesidades y sistema de target
Citizen.CreateThread(function()
    exports.ox_target:addGlobalObject({
        {
            name = 'check_door_id',
            icon = 'fas fa-door-open',
            label = 'Check Door ID',
            onSelect = function(data)
                local doorId = exports["doors_creator"]:getDoorIdFromEntity(data.entity)

                if doorId then
                    print("Found door with ID: " .. doorId)
                end
            end
        }
    })
end)
```
