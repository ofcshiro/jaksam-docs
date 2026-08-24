---
title: "Preguntas frecuentes"
description: "Preguntas frecuentes específicas de Doors Creator."
icon: "circle-question"
---

Esta página tiene preguntas frecuentes relacionadas **únicamente con este script** — asegúrate de revisar también las [preguntas frecuentes comunes](/es/jaksams-scripts/common-faq) para otros problemas.

<AccordionGroup>
  <Accordion title="No puedo seleccionar una puerta">
    Si no puedes seleccionar una puerta, significa que el modelo de la puerta no está en la lista de puertas permitidas.

    Para añadir el modelo de la puerta a la lista, pulsa **H** mientras seleccionas la puerta.

    Si aún no puedes seleccionar la puerta después de pulsar H, estas son las posibles razones:

    - Tienes un script que añade un arma a tu personaje
    - La puerta no es utilizable por alguna razón — si es un MLO modificado, esa es probablemente la causa

  </Accordion>

  <Accordion title="La puerta de la caja fuerte no funciona">
    Si una puerta en concreto no funciona con la opción de vault, prueba **tanto** las opciones de ratio como de heading.

    Para el heading, tendrás que encontrar por tu cuenta el valor que mejor se ajusta a esa puerta (0-360 son los valores mínimo/máximo), o usar el botón integrado del script para encontrarlo.

    Asegúrate de probar diferentes velocidades (como una velocidad más lenta).

    <Note>
      Si una puerta no funciona en absoluto, no hay nada que se pueda hacer.
    </Note>
  </Accordion>

  <Accordion title="Las puertas no están bloqueadas después de reiniciar">
    Si una puerta no está bloqueada cuando debería estarlo después de un reinicio del script/servidor, significa que activaste la opción de guardar el estado de bloqueo de la puerta en la configuración del menú del script.
  </Accordion>

  <Accordion title="No puedo confirmar una puerta nueva">
    Si no puedes confirmar una puerta nueva con la tecla ENTER, puedes editar los keybinds en el archivo `integrations/cl_integrations.lua`.
  </Accordion>
</AccordionGroup>
