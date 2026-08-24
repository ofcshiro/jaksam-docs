---
title: "Replace default notifications"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el evento notify."
icon: "bell"
---

Se activa después de notificar al jugador del lado cliente.

```lua Event
AddEventHandler("vehicles_keys:notify", function(message, uncoloredMessage)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Mensaje de la notificación                                  |
| `uncoloredMessage` | string    | Mensaje de la notificación pero sin `~r~`, `~g~`, etc.   |

## Ejemplo

```lua
RegisterNetEvent("vehicles_keys:framework:ready", function()
    -- Desactiva la notificación predeterminada del script (de lo contrario habría 2 notificaciones)
    exports["vehicles_keys"]:disableScriptEvent("vehicles_keys:notify")
end)

RegisterNetEvent("vehicles_keys:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
