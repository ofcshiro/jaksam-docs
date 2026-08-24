---
title: "Replace default notifications"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el event notify."
icon: "bell"
---

Se dispara después de notificar al jugador del lado del cliente.

```lua Event
AddEventHandler("races_creator:notify", function(message, uncoloredMessage)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Mensaje de la notificación                                  |
| `uncoloredMessage` | string    | Mensaje de la notificación pero sin `~r~`, `~g~`, etc.   |

## Ejemplo

```lua
RegisterNetEvent("races_creator:framework:ready", function()
    -- Deshabilita la notificación predeterminada del script (de lo contrario habría 2 notificaciones)
    exports["races_creator"]:disableScriptEvent("races_creator:notify")
end)

RegisterNetEvent("races_creator:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)

    -- O si NO quieres ~r~, ~g~ puedes usar
    --TriggerEvent("external_script:notify", uncoloredMessage)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
