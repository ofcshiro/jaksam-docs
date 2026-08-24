---
title: "Preguntas frecuentes"
description: "Preguntas frecuentes específicas de Vehicles Keys."
icon: "circle-question"
---

Esta página tiene preguntas frecuentes relacionadas **únicamente con este script** — asegúrate de revisar también las [preguntas frecuentes comunes](/es/jaksams-scripts/common-faq) para otros problemas.

<AccordionGroup>
  <Accordion title="Aviso de hitches / Rendimiento">
    Si tu servidor muestra hitches/problemas de rendimiento, es porque la opción `CONTINUOUSLY_REFRESH_PLAYERS_OWNED_VEHICLES` está activada en `vehicles_keys/integrations/sv_integrations.lua`.

    Si desactivas la opción, ya no causará problemas de rendimiento, pero tendrás que usar los exports de la documentación para actualizar los vehículos propios de un jugador (por ejemplo, después de que compre un vehículo nuevo en una tienda).

    Consulta la página [arreglar el puenteo de un coche comprado](/es/vehicles-keys/fix-hotwiring-bought-car) para ver **ejemplos** ya preparados.

    <Note>
      La integración con otros scripts externos depende completamente de ti.
    </Note>
  </Accordion>

  <Accordion title="No puedo entrar al vehículo">
    Si no puedes entrar a un vehículo después de destruir su ventana, significa que todavía tienes el script `qb-vehicleskeys` iniciado.

    Elimínalo para solucionar el problema.
  </Accordion>
</AccordionGroup>
