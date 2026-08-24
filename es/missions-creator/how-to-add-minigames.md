---
title: "Cómo añadir minijuegos"
description: "Añade tu propio minijuego personalizado a Missions Creator."
icon: "gamepad"
---

Añadir nuevos minijuegos es fácil. Sigue este procedimiento para añadir un nuevo minijuego:

<Steps>
  <Step title="Duplica el archivo de ejemplo">
    Duplica el archivo `missions_creator/client/minigames/_EXAMPLE_MINIGAME.lua`.
  </Step>
  <Step title="Renombra el archivo">
    Renombra el archivo con el nombre de tu minijuego.
  </Step>
  <Step title="Elimina los marcadores de comentario">
    Abre el nuevo archivo y elimina los comentarios al principio y al final del archivo (elimina los símbolos `--[[` y `--]]`).
  </Step>
  <Step title="Renombra el minijuego">
    Cambia `YOUR_MINIGAME_NAME` por el nombre de tu minijuego.
  </Step>
  <Step title="Implementa tu minijuego">
    Edita la función para que sea compatible con tu minijuego. Debe devolver `true` en caso de éxito y `false` en caso de fallo. Puedes ver ejemplos en `datacrack.lua`, `fingerprint.lua` y `memory_game.lua`.
  </Step>
  <Step title="Reinicia el script">
    Guarda el archivo y reinicia el script. Si todo se hizo correctamente (especialmente la implementación del minijuego en sí), deberías ver tu minijuego en la lista de minijuegos del script.
  </Step>
</Steps>
