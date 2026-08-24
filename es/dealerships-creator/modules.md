---
title: "Módulos"
description: "Reemplaza funciones por defecto como banca, text UI y logs con tus propios módulos personalizados."
icon: "puzzle-piece"
---

Los módulos son una forma sencilla de que Dealerships Creator reemplace ciertas funciones por defecto (banca, text UI, logs).

Para elegir un módulo existente, abre el menú `/dealershipscreator`, ve a ajustes, y elígelo. Así de fácil.

### Módulos disponibles

| Categoría | Opciones disponibles |
| --- | --- |
| Banca | `default`, `example`, `okokbanking` |
| Logs | `custom`, `jaksam` |
| Text UI | `esx`, `none`, `ox_lib` |

### Crear un módulo personalizado

Elige la categoría para la que quieres crear un módulo. Cada pestaña te guía paso a paso para esa categoría y te da una plantilla lista para editar.

<Tabs>
  <Tab title="Banca">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `dealerships_creator/_modules/banking`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo, `example`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "banking"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Devuelve el saldo actual de la cuenta de la sociedad/empresa indicada
        Integrations[moduleType][moduleName].getSocietyMoney = function(societyName)
            -- Añade tu código aquí
        end

        -- Añade dinero a la cuenta de la sociedad/empresa indicada
        Integrations[moduleType][moduleName].giveMoneyToSociety = function(societyName, amount)
            -- Añade tu código aquí
        end

        -- Quita dinero de la cuenta de la sociedad/empresa indicada
        Integrations[moduleType][moduleName].removeMoneyFromSociety = function(societyName, amount)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `dealerships_creator/_modules/logs`.
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

  <Tab title="Text UI">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `dealerships_creator/_modules/textui`.
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
