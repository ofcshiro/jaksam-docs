---
title: "Barra de progreso"
description: "Reemplaza la barra de progreso predeterminada por la tuya propia, o activa la predeterminada desde scripts externos."
icon: "spinner"
---

## Reemplazar/Desactivar

Se activa al usar la barra de progreso.

```lua Event
RegisterNetEvent("farming_creator:internalProgressBar", function(time, text)

end)
```

### Parámetros

| Nombre   | Tipo de dato | Descripción                       |
| ------ | --------- | ---------------------------------- |
| `time` | integer   | Duración de la barra de progreso en segundos   |
| `text` | string    | Texto de descripción                   |

### Ejemplo

```lua
-- En farming_creator/integrations/cl_integrations.lua
RegisterNetEvent("farming_creator:framework:ready", function()
    -- Desactiva la barra de progreso predeterminada del script (de lo contrario habría 2 barras de progreso)
    exports["farming_creator"]:disableScriptEvent("farming_creator:internalProgressBar")
end)

-- Ejemplo para reemplazar la barra de progreso del script por una externa
RegisterNetEvent("farming_creator:internalProgressBar", function(time, text)
    -- El event para activar tu barra de progreso externa
    TriggerEvent("external_progressbar:start", time, text)
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>

## Uso en scripts externos

Si te gusta la barra de progreso predeterminada del script y quieres usarla en scripts externos, este es el event:

```lua
TriggerEvent("farming_creator:startProgressBar", timeInMS, text, hexColor)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                                                                            |
| ---------- | --------- | --------------------------------------------------------------------------------------------------------- |
| `timeInMS` | integer   | Duración de la barra de progreso en milisegundos                                                              |
| `text`     | string    | El texto que se mostrará con la barra de progreso                                                         |
| `hexColor` | string    | El color de la barra de progreso en código hexadecimal (ejemplo `#70f2b4`). Puede ser `nil` para usar el color predeterminado del script |

### Ejemplo

```lua
-- Esto creará un comando para mostrar una barra de progreso roja
-- /progressbar 5000 Hello
RegisterCommand("progressbar", function(playerId, args)
    TriggerEvent("farming_creator:startProgressBar", tonumber(args[1]), args[2], "#ff0000")
end)
```
