---
title: "Replace default notifications"
description: "Usa un sistema de notificaciones personalizado en lugar del predeterminado escuchando el event notify."
icon: "bell"
---

Se dispara después de notificar al jugador del lado del cliente.

```lua Event
AddEventHandler("missions_creator:notify", function(message, coloredMessage)

end)
```

### Parámetros

| Nombre              | Tipo de dato | Descripción                                                |
| ----------------- | --------- | ------------------------------------------------------------ |
| `message`         | string    | Mensaje de la notificación pero sin `~r~`, `~g~`, etc.   |
| `coloredMessage`  | string    | Mensaje de la notificación                                  |

## Ejemplo

```lua
RegisterNetEvent("missions_creator:framework:ready", function()
    -- Deshabilita la notificación predeterminada del script (de lo contrario habría 2 notificaciones)
    exports["missions_creator"]:disableScriptEvent("missions_creator:notify")
end)

RegisterNetEvent("missions_creator:notify", function(message, coloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Coloca este código en el archivo `jaksam_core/config/cl_config.lua`, al final del archivo en líneas nuevas.
</Note>
