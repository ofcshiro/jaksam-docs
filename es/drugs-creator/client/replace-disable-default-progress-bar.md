---
title: "Progress bar"
description: "Reemplaza la barra de progreso por defecto con la tuya, o actívala desde scripts externos."
icon: "spinner"
---

## ¿Cómo reemplazarla?

Puedes usar un [módulo](/es/drugs-creator/modules) de Drugs Creator si quieres usar tu propia barra de progreso.

## Uso en scripts externos

Si te gusta la barra de progreso por defecto del script y quieres usarla en scripts externos, este es el event:

```lua
TriggerEvent("drugs_creator:startProgressBar", timeInMS, text, hexColor)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                                                                            |
| ---------- | --------- | --------------------------------------------------------------------------------------------------------- |
| `timeInMS` | integer   | Duración de la barra de progreso en milisegundos                                                              |
| `text`     | string    | El texto que se mostrará junto con la barra de progreso                                                         |
| `hexColor` | string    | El color de la barra de progreso en código hexadecimal (ejemplo `#70f2b4`). Puede ser `nil` para usar el color por defecto del script |

### Ejemplo

```lua
-- Esto creará un comando para mostrar una barra de progreso roja
-- /progressbar 5000 Hello
RegisterCommand("progressbar", function(playerId, args)
    TriggerEvent("drugs_creator:startProgressBar", tonumber(args[1]), args[2], "#ff0000")
end)
```
