---
title: "Módulos"
description: "Reemplaza funciones por defecto como la barra de progreso, dispatch y logs con tus propios módulos personalizados."
icon: "puzzle-piece"
---

Los módulos son una forma sencilla de que Robberies Creator reemplace ciertas funciones por defecto (barra de progreso, dispatch, logs).

Para elegir un módulo existente, abre el menú `/robberiescreator`, ve a ajustes, y elígelo. Así de fácil.

### Módulos disponibles

| Categoría | Opciones disponibles |
| --- | --- |
| Dispatch | `codesign`, `default`, `rcore`, `roadphone` |
| Logs | `custom`, `jaksam` |
| Barra de progreso | `jaksam`, `ox_lib`, `qb-core` |
| Text UI | `esx`, `none`, `ox_lib` |

### Crear un módulo personalizado

Elige la categoría para la que quieres crear un módulo. Cada pestaña te guía paso a paso para esa categoría y te da una plantilla lista para editar.

<Tabs>
  <Tab title="Dispatch">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `robberies_creator/_modules/dispatch`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo, `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "dispatch"
        local moduleName = "yourModuleName" -- Renombra según la integración que estás creando

        -- No tocar, necesario para aparecer en los ajustes in-game
        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Se ejecuta una vez por llamada, en el servidor
        Integrations[moduleType][moduleName].alertPoliceServerSide = function(coords, message, category)
            if not IsDuplicityVersion() then return end

            -- Añade tu código aquí (por ejemplo, llamar al export/event de tu script de dispatch para alertar a la policía)
        end

        -- Se ejecuta en el cliente, en el cliente de cada agente de policía
        Integrations[moduleType][moduleName].alertPoliceMemberClientSide = function(coords, message, category)
            if IsDuplicityVersion() then return end

            -- Añade tu código aquí (por ejemplo, mostrar un blip/notificación al agente)
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `robberies_creator/_modules/logs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo, `jaksam`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "logs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Envía una entrada de log (por ejemplo, a un webhook de Discord o a un script de logs personalizado)
        Integrations[moduleType][moduleName].log = function(playerId, title, description, type, logType)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Barra de progreso">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `robberies_creator/_modules/progressbar`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo, `jaksam`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "progressbar"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Inicia una barra de progreso durante el tiempo indicado (ms), con el texto y color indicados
        Integrations[moduleType][moduleName].start = function(time, text, hexColor)
            -- Añade tu código aquí
        end

        -- Detiene/oculta la barra de progreso
        Integrations[moduleType][moduleName].stop = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `robberies_creator/_modules/textui`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo, `ox_lib`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "textui"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Muestra un aviso de text UI con el mensaje indicado
        Integrations[moduleType][moduleName].show = function(message)
            -- Añade tu código aquí
        end

        -- Oculta el aviso de text UI
        Integrations[moduleType][moduleName].hide = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
