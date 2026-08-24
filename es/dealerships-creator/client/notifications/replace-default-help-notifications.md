---
title: "Reemplazar notificaciones de ayuda por defecto"
description: "Reemplaza la notificación de ayuda por defecto 'Press E to ...' con la tuya propia."
icon: "circle-info"
---

Se usa para mostrar el típico texto `Press E to ...` en la esquina superior izquierda de la pantalla del jugador.

```lua Export
exports["dealerships_creator"]:replaceShowHelpNotification(customFunction)
```

### Parámetros

| Nombre             | Tipo de dato | Descripción                                                                                                    |
| ---------------- | --------- | ------------------------------------------------------------------------------------------------------------- |
| `customFunction` | function  | Una función que reemplaza el método por defecto `ESX.ShowHelpNotification`. **Requiere** el parámetro message y se llama cada frame |

## Ejemplo

```lua
local function myCustomHelpNotification(message)
    -- Personaliza tu función según tus necesidades
    print(message)

    ExternalScript.showHelpNotification(message)
end

RegisterNetEvent("dealerships_creator:framework:ready", function()
    -- Esto reemplazará la función base con la que quieras
    exports["dealerships_creator"]:replaceShowHelpNotification(myCustomHelpNotification)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
