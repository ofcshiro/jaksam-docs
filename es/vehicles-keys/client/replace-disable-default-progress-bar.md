---
title: "Replace/Disable default progress bar"
description: "Reemplaza la barra de progreso predeterminada por la tuya propia, o activa la predeterminada desde scripts externos."
icon: "spinner"
---

Se activa al usar la barra de progreso.

```lua Event
RegisterNetEvent("vehicles_keys:internalProgressBar", function(time, text)

end)
```

### Parámetros

| Nombre   | Tipo de dato | Descripción                       |
| ------ | --------- | ------------------------------------ |
| `time` | integer   | Duración de la barra de progreso en segundos       |
| `text` | string    | Texto de descripción                        |

## Ejemplo

```lua
-- En vehicles_keys/integrations/cl_integrations.lua
RegisterNetEvent("vehicles_keys:framework:ready", function()
    -- Desactiva la barra de progreso predeterminada del script (de lo contrario habría 2 barras de progreso)
    exports["vehicles_keys"]:disableScriptEvent("vehicles_keys:internalProgressBar")
end)

-- Ejemplo para reemplazar la barra de progreso del script por una externa
RegisterNetEvent("vehicles_keys:internalProgressBar", function(time, text)
    -- El evento para activar tu barra de progreso externa
    TriggerEvent("external_progressbar:start", time, text)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
