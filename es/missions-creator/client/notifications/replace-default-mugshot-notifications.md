---
title: "Replace default mugshot notifications"
description: "Reemplaza la notificación mostrada para la acción 'hablar con ped' (con foto del NPC)."
icon: "id-card"
---

Notificación mostrada al usar la acción "hablar con ped" (notificación con foto del NPC).

```lua Event
AddEventHandler("missions_creator:internalMugshotNotify", function(ped, title, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                   |
| --------- | --------- | -------------------------------- |
| `ped`     | integer   | Handle de la entidad ped                |
| `title`   | string    | Título de la notificación         |
| `message` | string    | Mensaje de la notificación       |

## Ejemplo

```lua
RegisterNetEvent("missions_creator:framework:ready", function()
    -- Deshabilita la notificación predeterminada del script (de lo contrario habría 2 notificaciones)
    exports["missions_creator"]:disableScriptEvent("missions_creator:internalMugshotNotify")
end)

RegisterNetEvent("missions_creator:internalMugshotNotify", function(ped, title, message)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `jaksam_core/config/cl_config.lua`, al final del archivo en líneas nuevas.
</Note>
