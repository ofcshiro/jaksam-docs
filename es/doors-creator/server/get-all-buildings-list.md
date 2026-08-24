---
title: "Get all buildings list"
description: "Obtén los datos de todos los edificios del lado servidor."
icon: "list"
---

```lua Export
exports["doors_creator"]:getAllBuildings()
```

### Valor de retorno

Una tabla con los datos de todos los edificios.

## Ejemplo

```lua
Citizen.CreateThread(function()
    local buildings = exports["doors_creator"]:getAllBuildings()

    for k, buildingData in pairs(buildings) do
        if(buildingData.allowedJobs and buildingData.allowedJobs["police"]) then
            print(buildingData.label .. " is a police building")
        end
    end
end)
```
