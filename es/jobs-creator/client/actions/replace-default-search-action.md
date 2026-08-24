---
title: "Replace default search action"
description: "Usa una acción de búsqueda personalizada en lugar de la predeterminada creando un módulo de búsqueda."
icon: "magnifying-glass"
---

Por defecto, la acción de búsqueda usa el comportamiento de búsqueda integrado de Jobs Creator. Si quieres usar tu propio sistema de stash, safe o armory en su lugar, puedes reemplazarlo con un **módulo** personalizado.

## Cómo reemplazarla

<Steps>
  <Step title="Ve a la carpeta de módulos">
    Ve a la carpeta `jobs_creator/_modules`.
  </Step>
  <Step title="Busca el tipo de módulo de búsqueda">
    Busca el módulo de tipo **search** existente para usarlo como plantilla.
  </Step>
  <Step title="Duplica el módulo">
    Copia el módulo de búsqueda existente y pégalo en la misma carpeta.
  </Step>
  <Step title="Renombra la copia">
    Renombra la copia pegada para que coincida con tu integración (por ejemplo, `my_stash_search.lua`).
  </Step>
  <Step title="Abre el archivo">
    Abre el archivo recién renombrado.
  </Step>
  <Step title="Modifica los events">
    Edita el contenido del archivo para que llame a los events/exports de tu propio script de stash, safe o armory en lugar de los predeterminados.
  </Step>
  <Step title="Selecciona el módulo dentro del juego">
    Abre el menú `/jobscreator`, ve a los ajustes y elige tu nuevo módulo para el job.
  </Step>
</Steps>

<Note>
  Para más detalles sobre cómo funcionan los módulos en general, consulta la página de [Módulos](/es/jobs-creator/modules).
</Note>
