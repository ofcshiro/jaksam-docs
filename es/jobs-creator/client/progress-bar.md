---
title: "Progress bar"
description: "Reemplaza la progress bar por defecto con la tuya propia, o usa la integrada en scripts externos."
icon: "spinner"
---

## Cómo reemplazarla

Puedes usar un [módulo](/es/jobs-creator/modules) de Jobs Creator si quieres usar tu propia progress bar.

<Steps>
  <Step title="Ve a la carpeta de módulos">
    Ve a la carpeta `jobs_creator/_modules`.
  </Step>
  <Step title="Busca el tipo de módulo progressbar">
    Busca el módulo de tipo **progressbar** existente para usarlo como plantilla.
  </Step>
  <Step title="Duplica el módulo">
    Copia el módulo progressbar existente y pégalo en la misma carpeta.
  </Step>
  <Step title="Renombra la copia">
    Renombra la copia pegada para que coincida con tu integración (por ejemplo, `my_progressbar.lua`).
  </Step>
  <Step title="Abre el archivo">
    Abre el archivo recién renombrado.
  </Step>
  <Step title="Modifica los events">
    Edita el contenido del archivo para que llame a los events/exports de tu propio script de progress bar en lugar del predeterminado.
  </Step>
  <Step title="Selecciona el módulo dentro del juego">
    Abre el menú `/jobscreator`, ve a los ajustes y elige tu nuevo módulo para el job.
  </Step>
</Steps>

## Uso en scripts externos

Si te gusta la progress bar por defecto del script y quieres usarla en scripts externos, este es el event:

<CodeGroup>

```lua Event
TriggerEvent("jobs_creator:startProgressBar", timeInMS, text, hexColor)
```

```lua Example
-- Esto creará un comando para mostrar una progressbar roja
-- /progressbar 5000 Hello
RegisterCommand("progressbar", function(playerId, args)
    TriggerEvent("jobs_creator:startProgressBar", tonumber(args[1]), args[2], "#ff0000")
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `timeInMS` | integer | Duración de la progress bar en milisegundos |
| `text` | string | El texto que se mostrará junto con la progress bar |
| `hexColor` | string | El color de la progress bar en código hexadecimal (ejemplo `#70f2b4`). Puede ser `nil` para usar el predeterminado del script |
