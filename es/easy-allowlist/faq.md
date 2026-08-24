---
title: "FAQ"
description: "Preguntas frecuentes específicas de Easy Allowlist & Queue."
icon: "circle-question"
---

Esta página contiene FAQs relacionadas **únicamente con este script** — asegúrate de revisar también las [FAQ comunes](/es/jaksams-scripts/common-faq) para otros problemas.

<AccordionGroup>
  <Accordion title="Cómo añadirme a la allowlist">
    El script detectará automáticamente si la allowlist está completamente vacía, así que se te dará whitelist automáticamente la primera vez que te conectes.

    Para dar whitelist manualmente, envía la solicitud de allowlist a tu servidor y luego usa el comando `add_allowlist YourRequestIdHere` en la consola del servidor.
  </Accordion>

  <Accordion title="Se queda atascado en 'deferring connection...'">
    Si al conectarte a tu servidor, Easy Allowlist muestra `deferring connection...` y se queda atascado sin ningún error, prueba esto:

    <Steps>
      <Step title="Abre el archivo de deferrals">
        Abre el archivo `easy_allowlist/server/deferrals.lua`.
      </Step>
      <Step title="Busca el wait">
        Busca el código `Citizen.Wait(500)`.
      </Step>
      <Step title="Aumenta el wait">
        Cámbialo de `Citizen.Wait(500)` a `Citizen.Wait(10000)` o más alto si sigue sin funcionar.
      </Step>
      <Step title="Guarda y reinicia">
        Guarda el archivo y reinicia el script.
      </Step>
    </Steps>
  </Accordion>
</AccordionGroup>
