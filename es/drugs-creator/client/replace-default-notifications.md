---
title: "Replace default notifications"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el event notify."
icon: "bell"
---

Se activa tras notificar al jugador del lado del cliente.

```lua Event
AddEventHandler("drugs_creator:notify", function(message, coloredMessage)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                                |
| ------------------- | --------- | ------------------------------------------------------------ |
| `message`           | string    | Mensaje de la notificación (sin color)                        |
| `coloredMessage`    | string    | Mensaje de la notificación pero con `~r~`, `~g~`, etc.        |

## Ejemplo

```lua
RegisterNetEvent("drugs_creator:framework:ready", function()
    -- Desactiva la notificación por defecto del script (de lo contrario habría 2 notificaciones)
    exports["drugs_creator"]:disableScriptEvent("drugs_creator:notify")
end)

RegisterNetEvent("drugs_creator:notify", function(message, coloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
