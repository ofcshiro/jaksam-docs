---
title: "Replace default help notifications"
description: "Reemplaza la notificación de ayuda predeterminada 'Press E to ...' con la tuya propia."
icon: "circle-info"
---

Se usa para mostrar el texto habitual `Press E to ...` en la esquina superior izquierda de la pantalla del jugador.

```lua Export
exports["missions_creator"]:replaceShowHelpNotification(customFunction)
```

### Parámetros

| Nombre             | Tipo de dato | Descripción                                                                                                    |
| ---------------- | --------- | ------------------------------------------------------------------------------------------------------------- |
| `customFunction` | function  | Una función que reemplaza el método predeterminado `ESX.ShowHelpNotification`. **Requiere** el parámetro message y se llama en cada frame |

## Ejemplo

```lua
local function myCustomHelpNotification(message)
    -- Personaliza tu función según tus necesidades
    print(message)

    ExternalScript.showHelpNotification(message)
end

RegisterNetEvent("missions_creator:framework:ready", function()
    -- Esto reemplazará la función base con la que quieras
    exports["missions_creator"]:replaceShowHelpNotification(myCustomHelpNotification)
end)
```

<Note>
  Coloca este código en el archivo `jaksam_core/config/cl_config.lua`, al final del archivo en líneas nuevas.
</Note>
