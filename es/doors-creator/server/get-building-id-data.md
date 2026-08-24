---
title: "Get building ID data"
description: "Obtén los datos de un edificio del lado servidor por su ID."
icon: "building"
---

```lua Export
exports["doors_creator"]:getBuildingIdData(buildingId)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                       |
| ------------ | --------- | ------------------------------------ |
| `buildingId` | integer   | El ID del edificio del que obtener los datos    |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local buildingId = 55
    local buildingData = exports["doors_creator"]:getBuildingIdData(buildingId)

    print("The name of building " .. buildingId .. " is " .. buildingData.label)
end)
```
