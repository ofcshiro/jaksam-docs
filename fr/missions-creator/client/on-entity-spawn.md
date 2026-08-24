---
title: "On entity spawn"
description: "Se déclenche côté client quand une mission fait apparaître un ped, un véhicule ou un objet."
icon: "cube"
---

```lua Event
RegisterNetEvent("missions_creator:entitySpawned", function(entityType, entity)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                    |
| ------------ | --------- | -------------------------------- |
| `entityType` | string    | `ped` / `vehicle` / `object`     |
| `entity`     | integer   | Le handle de l'entité               |

## Exemple

```lua
-- Juste un exemple que tu peux modifier pour donner des clés aux véhicules générés
RegisterNetEvent("missions_creator:entitySpawned", function(entityType, entity)
    if(entityType == "vehicle") then
        local plate = GetVehicleNumberPlateText(entity)
        TriggerEvent("GIVEKEYS", plate)
    end
end)
```

<Note>
  Place ce code dans le fichier `jaksam_core/config/cl_config.lua`, en bas du fichier sur de nouvelles lignes.
</Note>
