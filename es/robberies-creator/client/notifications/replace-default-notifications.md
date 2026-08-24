---
title: "Reemplazar notificaciones por defecto"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el event notify."
icon: "bell"
---

Se activa después de notificar al jugador en el cliente.

```lua Event
AddEventHandler("robberies_creator:notify", function(message, uncoloredMessage)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Mensaje de la notificación                                  |
| `uncoloredMessage` | string    | Mensaje de la notificación pero sin `~r~`, `~g~`, etc.   |

## Ejemplo

```lua
RegisterNetEvent("robberies_creator:framework:ready", function()
    -- Desactiva la notificación por defecto del script (si no, habría 2 notificaciones)
    exports["robberies_creator"]:disableScriptEvent("robberies_creator:notify")
end)

RegisterNetEvent("robberies_creator:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)

    -- O si NO quieres ~r~, ~g~ puedes usar
    --TriggerEvent("external_script:notify", uncoloredMessage)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
