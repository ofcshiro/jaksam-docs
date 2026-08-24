---
title: "Replace default help notifications"
description: "Reemplaza la notificación de ayuda predeterminada 'Press E to ...' por la tuya propia."
icon: "circle-info"
---

Se usa para mostrar el típico texto `Press E to ...` en la parte superior izquierda de la pantalla del jugador.

```lua Export
exports["vehicles_keys"]:replaceShowHelpNotification(customFunction)
```

### Parámetros

| Nombre             | Tipo de dato | Descripción                                                                                                    |
| ---------------- | --------- | ------------------------------------------------------------------------------------------------------------- |
| `customFunction` | function  | Una función que reemplaza el método predeterminado `ESX.ShowHelpNotification`. **Requiere** el parámetro message y se llama cada frame |

## Ejemplo

```lua
local function myCustomHelpNotification(message)
    -- Personaliza tu función según tus necesidades
    print(message)

    ExternalScript.showHelpNotification(message)
end

RegisterNetEvent("vehicles_keys:framework:ready", function()
    -- Esto reemplazará la función base por la que tú quieras
    exports["vehicles_keys"]:replaceShowHelpNotification(myCustomHelpNotification)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
