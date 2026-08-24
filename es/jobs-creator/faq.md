---
title: "FAQ"
description: "Preguntas frecuentes específicas de Jobs Creator, sobre animaciones, salarios, outfits y errores comunes de configuración."
icon: "circle-question"
---

Esta página contiene FAQs relacionadas **ÚNICAMENTE con este script**. Asegúrate de revisar también la [FAQ común](/es/jaksams-scripts/common-faq) para otros problemas.

<AccordionGroup>
  <Accordion title="Cómo cambiar las animaciones">
    [Esta es una lista de animaciones que puedes usar](https://alexguirre.github.io/animations-list/)

    - El texto más grande es el diccionario de la animación
    - El texto más pequeño es el nombre de la animación

    [Esta es la lista de escenarios que puedes usar](https://wiki.rage.mp/index.php?title=Scenarios)

    La principal diferencia entre escenarios y animaciones es que un escenario suele tener un objeto asociado a la animación.

    _No es posible usar animaciones externas._

    <Note>
      No todas las animaciones de las listas funcionan.
    </Note>
  </Accordion>

  <Accordion title="Cómo bloquear los vehículos de los jobs">
    Para bloquear vehículos tienes 2 opciones:

    1. Usar los events y exports de la documentación del script para integrar tu propio script de bloqueo de vehículos
    2. Usar **jaksam's Vehicles Keys**, que incluye integración con Jobs Creator

    _Nota: la integración de scripts externos depende completamente de ti._
  </Accordion>

  <Accordion title="¿Cómo gestiona Jobs Creator los salarios/sueldos?">
    Jobs Creator no gestiona los salarios, ya que eso lo hace el script del framework:

    - En ESX, los scripts `es_extended` y `esx_society` gestionan los salarios
    - En QBCore, `qb-core` gestiona los salarios

    Así que podrás **definir** los salarios en Jobs Creator, pero es el framework el que paga el dinero.
  </Accordion>

  <Accordion title='Cómo solucionar el error "Couldnt create marker"'>
    Este problema está causado por algo mal configurado en la tabla `job_data` de la base de datos.

    Posibles soluciones:

    1. Elimina la tabla `job_data` de la base de datos y reinicia el script/servidor
    2. Si la columna `id` de la tabla `job_data` no tiene **AUTO INCREMENT** como valor por defecto, configura esa columna para que lo tenga
  </Accordion>

  <Accordion title="¿Por qué no funcionan las funciones de outfits?">
    Si las funciones de outfits no funcionan, es porque no tienes las dependencias necesarias:

    - En ESX, debes tener instalados los scripts `esx_skin` y `skinchanger`
    - En QBCore, debes tener instalado el script `qb-clothing`

    Jobs Creator tiene integración con [**illenium-appearance**](https://github.com/iLLeniumStudios/illenium-appearance), que debería funcionar en ambos frameworks.
  </Accordion>

  <Accordion title="El mejorador de armas no funciona">
    Si el marcador del mejorador de armas no funciona, hay 2 posibles razones:

    1. Estás usando un arma addon, pero no la has configurado correctamente en el script `es_extended`
    2. Tu inventario modifica el comportamiento estándar de **ESX/QBCore**, en este caso debes usar tu propio inventario en lugar de Jobs Creator para los componentes y tintes de armas
  </Accordion>

  <Accordion title="Editar las etiquetas de vehículos en los garages">
    Jobs Creator obtiene las etiquetas de los vehículos mediante natives de FiveM, así que para tener etiquetas personalizadas tendrás que configurarlas en tu script de vehículos addon.

    Hay varias guías en los foros de FiveM sobre cómo configurar los nombres de visualización de vehículos addon.
  </Accordion>

  <Accordion title="QBCore no reconoce los jobs de Jobs Creator">
    Normalmente no es necesario añadir ningún código. Aun así, un orden de inicio de scripts diferente puede provocar que otros scripts no reconozcan los jobs de Jobs Creator en QBCore.

    **¿Cómo puedo solucionar esto?**

    La solución es muy sencilla: añade el siguiente event **tanto en el cliente como en el servidor** en el script que no reconoce los jobs de Jobs Creator.

    ```lua
        -- Integración de jaksam's Jobs Creator
        AddEventHandler('jobs_creator:injectJobs', function(jobs)
            -- Asigna los nuevos jobs al objeto de QBCore, la siguiente línea depende de cómo esté estructurado tu script
            QBCore.Shared.Jobs = jobs
        end)
    ```
  </Accordion>
</AccordionGroup>
