---
title: "Módulos"
description: "Reemplaza funciones predeterminadas como lockpick, dispatch y logs con tus propios módulos personalizados."
icon: "puzzle-piece"
---

Los módulos son una forma sencilla de que Doors Creator reemplace ciertas funciones predeterminadas (lockpick, dispatch, logs).

Para elegir un módulo existente, abre el menú `/doorscreator`, ve a settings y elígelo. Eso es todo.

### Módulos disponibles

| Categoría | Opciones disponibles |
| --- | --- |
| Dispatch | `codesign`, `default`, `rcore`, `roadphone` |
| Gangs | `default` |
| Lockpick | `default`, `ox_lib` |
| Logs | `custom`, `jaksam` |
| Progress Bar | `jaksam`, `ox_lib`, `qb-core` |
| Text UI | `esx`, `none`, `ox_lib` |

### Crear un módulo personalizado

Elige la categoría para la que quieres crear un módulo. Cada pestaña te guía por los pasos exactos de esa categoría y te da una plantilla lista para editar.

<Tabs>
  <Tab title="Dispatch">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `doors_creator/_modules/dispatch`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los eventos del script de terceros que estás integrando:

        ```lua
        local moduleType = "dispatch"
        local moduleName = "yourModuleName" -- Renómbralo para que coincida con la integración que estás creando

        -- No lo toques, es necesario para que aparezca en la configuración del juego
        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Se ejecuta una vez por llamada, del lado servidor
        Integrations[moduleType][moduleName].alertPoliceServerSide = function(coords, message, category)
            if not IsDuplicityVersion() then return end

            -- Añade tu código aquí (por ejemplo, llamar al export/event de tu script de dispatch para alertar a la policía)
        end

        -- Se ejecuta del lado cliente, en el cliente de cada oficial de policía
        Integrations[moduleType][moduleName].alertPoliceMemberClientSide = function(coords, message, category)
            if IsDuplicityVersion() then return end

            -- Añade tu código aquí (por ejemplo, mostrar un blip/notificación al oficial)
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Gangs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `doors_creator/_modules/gangs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los eventos del script de terceros que estás integrando:

        ```lua
        local moduleType = "gangs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Comprueba si un jugador tiene permiso para abrir una puerta según su gang y nivel de grade, DEL LADO SERVIDOR
        -- Formato de allowedGangs: { gangName = true } (todos los grades permitidos) o { gangName = { ["0"] = true, ["1"] = true } } (grades específicos)
        Integrations[moduleType][moduleName].isPlayerGangAllowedToOpenDoor = function(playerId, allowedGangs)
            -- Añade tu código aquí
        end

        -- Devuelve todas las gangs disponibles en el juego (consulta un módulo existente para el formato exacto de la tabla)
        Integrations[moduleType][moduleName].getAllGangs = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Lockpick">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `doors_creator/_modules/lockpick`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los eventos del script de terceros que estás integrando:

        ```lua
        local moduleType = "lockpick"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Inicia el minijuego de lockpick con el número de intentos indicado, y devuelve si tuvo éxito
        Integrations[moduleType][moduleName].startLockpick = function(attempts)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `doors_creator/_modules/logs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `jaksam`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los eventos del script de terceros que estás integrando:

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

  <Tab title="Progress Bar">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `doors_creator/_modules/progressbar`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `jaksam`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los eventos del script de terceros que estás integrando:

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
        Ve a la carpeta `doors_creator/_modules/textui`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `ox_lib`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones requeridas">
        Abre el archivo renombrado y edítalo para que coincida con los eventos del script de terceros que estás integrando:

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
