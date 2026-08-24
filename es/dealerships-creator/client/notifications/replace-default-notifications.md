---
title: "Reemplazar notificaciones por defecto"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el event notify."
icon: "bell"
---

Se activa después de notificar al jugador en el cliente.

```lua Event
AddEventHandler("dealerships_creator:notify", function(message, coloredMessage)

end)
```

### Parámetros

| Nombre              | Tipo de dato | Descripción                                              |
| ------------------ | --------- | ----------------------------------------------------------- |
| `message`          | string    | Mensaje de la notificación                                  |
| `coloredMessage`   | string    | Mensaje de la notificación pero con `~r~`, `~g~`, etc.       |

## Ejemplo

```lua
RegisterNetEvent("dealerships_creator:framework:ready", function()
    -- Desactiva la notificación por defecto del script (si no, habría 2 notificaciones)
    exports["dealerships_creator"]:disableScriptEvent("dealerships_creator:notify")
end)

RegisterNetEvent("dealerships_creator:notify", function(message, coloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
