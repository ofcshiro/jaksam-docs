---
title: "Reemplazar las notificaciones predeterminadas"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el event notify."
icon: "bell"
---

Se activa después de notificar al jugador del lado del cliente.

```lua Event
AddEventHandler("luxury_clothes_theft:notify", function(message, uncoloredMessage)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Mensaje de la notificación                                  |
| `uncoloredMessage` | string    | Mensaje de la notificación pero sin `~r~`, `~g~`, etc.   |

## Ejemplo

```lua
RegisterNetEvent("luxury_clothes_theft:framework:ready", function()
    -- Desactiva la notificación predeterminada del script (de lo contrario habría 2 notificaciones)
    exports["luxury_clothes_theft"]:disableScriptEvent("luxury_clothes_theft:notify")
end)

RegisterNetEvent("luxury_clothes_theft:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
