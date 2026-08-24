---
title: "FAQ"
description: "Preguntas frecuentes específicas de Drugs Creator."
icon: "circle-question"
---

Esta página contiene FAQs relacionadas **únicamente con este script** — asegúrate de revisar también las [FAQ comunes](/es/jaksams-scripts/common-faq) para otros problemas.

<AccordionGroup>
  <Accordion title="Los efectos de las drogas no funcionan">
    Si los efectos no funcionan, significa que la función `ESX.RegisterUsableItem` de tu `es_extended` no está funcionando correctamente.

    Aun así puedes registrar/activar los efectos manualmente usando el event [manually start drugs effects](/es/drugs-creator/client/manually-start-drugs-effects).

    Tanto en **ESX** como en **QBCore**, un anticheat puede interferir con los efectos de las drogas.

    <Note>
      Esto no depende del script, y no podemos solucionarlo por ti.
    </Note>
  </Accordion>

  <Accordion title="Mal rendimiento">
    Si tienes problemas de rendimiento en el servidor con Drugs Creator, lo más probable es que se deba a la venta a NPCs, que requiere actualizar el inventario de todos los jugadores para poder mostrar el diálogo `Press E to sell drugs`.

    Para mejorar el rendimiento, activa la opción correspondiente en la configuración ingame del script, para que use el NPC más cercano o genere uno (según tu configuración).
  </Accordion>
</AccordionGroup>
