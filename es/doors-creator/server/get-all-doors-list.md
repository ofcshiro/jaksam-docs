---
title: "Get all doors list"
description: "Obtén los datos de todas las puertas del lado servidor."
icon: "list"
---

```lua Export
exports["doors_creator"]:getAllDoors()
```

### Valor de retorno

Una tabla con los datos de todas las puertas.

## Ejemplo

```lua
Citizen.CreateThread(function()
    local doors = exports["doors_creator"]:getAllDoors()

    for k, doorData in pairs(doors) do
        if(doorData.allowedJobs and doorData.allowedJobs["police"]) then
            print(doorData.id .. " is a police door")
        end
    end
end)
```
