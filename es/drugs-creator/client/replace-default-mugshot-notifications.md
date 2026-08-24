---
title: "Replace default mugshot notifications"
description: "Reemplaza la notificación mostrada cuando un ped rechaza una droga durante la venta a NPCs."
icon: "id-card"
---

Notificación mostrada cuando un ped rechaza la droga en la venta a NPCs (notificación con la cara del ped).

```lua Event
AddEventHandler("drugs_creator:internalMugshotNotify", function(ped, title, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                   |
| --------- | --------- | ---------------------------------- |
| `ped`     | integer   | Handle de la entidad del ped                     |
| `title`   | string    | Título de la notificación               |
| `message` | string    | Mensaje de la notificación              |

## Ejemplo

```lua
RegisterNetEvent("drugs_creator:framework:ready", function()
    -- Desactiva la notificación por defecto del script (de lo contrario habría 2 notificaciones)
    exports["drugs_creator"]:disableScriptEvent("drugs_creator:internalMugshotNotify")
end)

RegisterNetEvent("drugs_creator:internalMugshotNotify", function(ped, title, message)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
