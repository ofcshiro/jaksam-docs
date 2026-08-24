---
title: "Replace help notification/TextUI"
description: "Usa un sistema de TextUI personalizado en lugar del predeterminado creando un módulo notify."
icon: "message"
---

Se usa para mostrar el típico aviso `Press E to ...` en la parte superior izquierda de la pantalla del jugador.

## Cómo reemplazarlo

<Steps>
  <Step title="Ve a la carpeta de módulos">
    Ve a la carpeta `jobs_creator/_modules`.
  </Step>
  <Step title="Busca el tipo de módulo notify">
    Busca el módulo de tipo **notify** existente para usarlo como plantilla.
  </Step>
  <Step title="Duplica el módulo">
    Copia el módulo notify existente y pégalo en la misma carpeta.
  </Step>
  <Step title="Renombra la copia">
    Renombra la copia pegada para que coincida con tu integración (por ejemplo, `my_textui.lua`).
  </Step>
  <Step title="Abre el archivo">
    Abre el archivo recién renombrado.
  </Step>
  <Step title="Modifica los events">
    Edita el contenido del archivo para que llame a los events/exports de tu propio script de TextUI en lugar del predeterminado.
  </Step>
  <Step title="Selecciona el módulo dentro del juego">
    Abre el menú `/jobscreator`, ve a los ajustes y elige tu nuevo módulo para el job.
  </Step>
</Steps>

<Note>
  Para más detalles sobre cómo funcionan los módulos en general, consulta la página de [Módulos](/es/jobs-creator/modules).
</Note>
