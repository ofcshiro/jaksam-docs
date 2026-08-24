---
title: "On entity spawn"
description: "Se dispara del lado del cliente cuando una misión genera un ped, vehículo u objeto."
icon: "cube"
---

```lua Event
RegisterNetEvent("missions_creator:entitySpawned", function(entityType, entity)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                    |
| ------------ | --------- | -------------------------------- |
| `entityType` | string    | `ped` / `vehicle` / `object`     |
| `entity`     | integer   | El handle de la entidad               |

## Ejemplo

```lua
-- Solo un ejemplo que puedes editar para dar llaves a los vehículos generados
RegisterNetEvent("missions_creator:entitySpawned", function(entityType, entity)
    if(entityType == "vehicle") then
        local plate = GetVehicleNumberPlateText(entity)
        TriggerEvent("GIVEKEYS", plate)
    end
end)
```

<Note>
  Coloca este código en el archivo `jaksam_core/config/cl_config.lua`, al final del archivo en líneas nuevas.
</Note>
