---
title: "Módulos"
description: "Reemplaza funciones predeterminadas como gangs, barra de progreso, text UI y logs con tus propios módulos personalizados."
icon: "puzzle-piece"
---

Los módulos son una forma sencilla de que Jaksam Inventory reemplace ciertas funciones predeterminadas (gangs, barra de progreso, text UI, logs).

Para elegir un módulo existente, abre el menú de administración `/inventory`, ve a settings y selecciónalo. Así de fácil.

### Módulos Disponibles

| Categoría | Opciones Disponibles |
| --- | --- |
| Gangs | `default` |
| Logs | `custom`, `jaksam` |
| Barra de Progreso | `jaksam`, `ox_lib`, `qb-core` |
| Text UI | `esx`, `none`, `ox_lib` |

### Crear un Módulo Personalizado

Elige la categoría para la que quieres crear un módulo. Cada pestaña te guía paso a paso por el proceso exacto para esa categoría y te ofrece una plantilla lista para editar.

<Tabs>
  <Tab title="Gangs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jaksam_inventory/_modules/gangs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (p. ej. `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "gangs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Comprueba si un jugador tiene permiso de gang según su gang y nivel de grado, LADO SERVIDOR
        -- Formato de allowedGangs: { gangName = true } (todos los grados permitidos) o { gangName = { ["0"] = true, ["1"] = true } } (grados específicos)
        Integrations[moduleType][moduleName].isPlayerGangAllowed = function(playerId, allowedGangs)
            -- Agrega tu código aquí
        end

        -- La misma comprobación, pero LADO CLIENTE
        Integrations[moduleType][moduleName].isClientGangAllowed = function(allowedGangs)
            -- Agrega tu código aquí
        end

        -- Devuelve todas las gangs disponibles en el juego (consulta un módulo existente para ver el formato exacto de la tabla)
        Integrations[moduleType][moduleName].getAllGangs = function()
            -- Agrega tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jaksam_inventory/_modules/logs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (p. ej. `jaksam`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "logs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Envía una entrada de log (p. ej. a un webhook de Discord o a un script de logs personalizado)
        Integrations[moduleType][moduleName].log = function(playerId, title, description, type, logType)
            -- Agrega tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Barra de Progreso">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jaksam_inventory/_modules/progressbar`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (p. ej. `jaksam`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "progressbar"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Inicia una barra de progreso durante el tiempo indicado (ms), con el texto y color dados
        Integrations[moduleType][moduleName].start = function(time, text, hexColor)
            -- Agrega tu código aquí
        end

        -- Detiene/oculta la barra de progreso
        Integrations[moduleType][moduleName].stop = function()
            -- Agrega tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jaksam_inventory/_modules/textui`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (p. ej. `ox_lib`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "textui"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Muestra un mensaje de text UI con el mensaje indicado
        Integrations[moduleType][moduleName].show = function(message)
            -- Agrega tu código aquí
        end

        -- Oculta el mensaje de text UI
        Integrations[moduleType][moduleName].hide = function()
            -- Agrega tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
