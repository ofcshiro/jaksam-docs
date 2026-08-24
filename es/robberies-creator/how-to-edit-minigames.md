---
title: "Cómo editar minijuegos"
description: "Añade tu propio minijuego personalizado a Robberies Creator."
icon: "gamepad"
---

Puedes añadir cualquier minijuego que quieras — hacerlo requerirá un mínimo de conocimientos de programación por tu parte.

<Steps>
  <Step title="Crea tu archivo de minijuego">
    Añade tu archivo de minijuego en `integrations/minigames` y crea tu función (usando `datacrack.lua`, o cualquier otro minijuego existente, como ejemplo).
  </Step>
  <Step title="Registra el minijuego">
    Edita el archivo `integrations/cl_hack_minigame.lua` para dar soporte a tu minijuego.
  </Step>
  <Step title="Añádelo a la interfaz">
    Edita `html/index.js`, busca `"datacrack"`, y añade tu minijuego ahí también.
  </Step>
</Steps>
