---
title: "Módulos"
description: "Reemplaza funciones por defecto como notify, progress bar, stash y logs con tus propios módulos personalizados."
icon: "puzzle-piece"
---

Los módulos son una forma sencilla de que Jobs Creator reemplace ciertas funciones por defecto (notify, progress bar, stash, logs).

Para elegir un módulo existente, abre el menú `/jobscreator`, ve a los ajustes y selecciónalo. Así de fácil.

### Módulos Disponibles

| Categoría | Opciones Disponibles |
| --- | --- |
| Banking | `default`, `example`, `okok` |
| Boss | `default`, `example` |
| Logs | `custom`, `jaksam` |
| Notify | `default`, `example`, `origen`, `ox_lib` |
| Outfits | `default`, `illenium-appearance`, `rcore_clothing` |
| Progress Bar | `jaksam`, `ox_lib`, `qb-core` |
| Search Player | `jaksam`, `jaksam_inventory`, `ox_inventory` |
| Skillcheck | `jaksam`, `ox_lib` |
| Stash | `default`, `hc_inventory`, `jaksam_inventory`, `ox-inventory`, `qb-inventory` |
| Text UI | `esx`, `jg-text`, `none`, `ox_lib` |

### Crear un Módulo Personalizado

Elige la categoría para la que quieres crear un módulo. Cada pestaña te guía paso a paso por el proceso exacto para esa categoría y te da una plantilla lista para editar.

<Tabs>
  <Tab title="Banking">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/banking`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `example`) y pégalo en la misma carpeta como plantilla.
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

        -- Devuelve el saldo actual de la cuenta de la sociedad/negocio indicada
        Integrations[moduleType][moduleName].getSocietyMoney = function(societyName)
            -- Añade tu código aquí
        end

        -- Añade dinero a la cuenta de la sociedad/negocio indicada
        Integrations[moduleType][moduleName].giveMoneyToSociety = function(societyName, amount)
            -- Añade tu código aquí
        end

        -- Quita dinero de la cuenta de la sociedad/negocio indicada
        Integrations[moduleType][moduleName].removeMoneyFromSociety = function(societyName, amount)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Boss">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/boss`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `example`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando. Las cuatro funciones son overrides opcionales: devolver `nil` deja intacto el comportamiento por defecto de Jobs Creator.

        ```lua
        local moduleType = "boss"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Se llama antes de devolver la lista de empleados al cliente, devuelve la lista (opcionalmente modificada)
        Integrations[moduleType][moduleName].modifyEmployeesList = function(employeesArray, jobName)
            -- Añade tu código aquí

            return employeesArray
        end

        -- Se llama al despedir a un empleado. Devuelve true si lo has gestionado tú mismo, nil para mantener el comportamiento por defecto
        Integrations[moduleType][moduleName].fireEmployee = function(playerId, employeeIdentifier, jobName)
            -- Añade tu código aquí

            return nil
        end

        -- Se llama antes de reclutar a un jugador. Devuelve true si lo has gestionado tú mismo, nil para mantener el comportamiento por defecto
        Integrations[moduleType][moduleName].recruitPlayer = function(playerId, targetId, jobName)
            -- Añade tu código aquí

            return nil
        end

        -- Se llama antes de cambiar el grado de un empleado. Devuelve true si lo has gestionado tú mismo, nil para mantener el comportamiento por defecto
        Integrations[moduleType][moduleName].changeGradeToEmployee = function(playerId, employeeIdentifier, newGrade, jobName)
            -- Añade tu código aquí

            return nil
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/logs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `jaksam`) y pégalo en la misma carpeta como plantilla.
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

  <Tab title="Notify">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/notify`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `example`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "notify"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Muestra una notificación con un mensaje plano y una versión (opcionalmente) coloreada de este
        Integrations[moduleType][moduleName].showNotification = function(message, coloredMessage)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Outfits">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/outfits`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `rcore_clothing`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando. `openExternalMenu` controla el resto: devuelve `true` para reemplazar por completo la interfaz de outfits con tu propio script (solo se usan `openWardrobe`/`openJobOutfits`), o `false` para seguir usando el menú de Jobs Creator (en su lugar se usan `getPlayerClothes`/`setPlayerClothes`).

        ```lua
        local moduleType = "outfits"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Devuelve true para reemplazar por completo la interfaz de outfits con tu propio script, false para seguir usando el menú de Jobs Creator
        Integrations[moduleType][moduleName].openExternalMenu = function()
            return false
        end

        -- Abre el menú de outfits guardados de tu script (solo se usa si openExternalMenu devuelve true)
        Integrations[moduleType][moduleName].openWardrobe = function()
            -- Añade tu código aquí
        end

        -- Abre el menú de outfits de job guardados de tu script, reemplazando por completo la función de outfits de job de Jobs Creator (solo se usa si openExternalMenu devuelve true)
        Integrations[moduleType][moduleName].openJobOutfits = function()
            -- Añade tu código aquí
        end

        -- Devuelve la tabla del outfit/ropa actual del jugador (solo se usa si openExternalMenu devuelve false)
        Integrations[moduleType][moduleName].getPlayerClothes = function()
            -- Añade tu código aquí
        end

        -- Aplica la tabla de outfit/ropa indicada al jugador (solo se usa si openExternalMenu devuelve false)
        Integrations[moduleType][moduleName].setPlayerClothes = function(outfit, saveAfterRestart)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Progress Bar">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/progressbar`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `jaksam`) y pégalo en la misma carpeta como plantilla.
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
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Search Player">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/search_player`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `ox_inventory`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "search_player"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Abre la interfaz de búsqueda/inventario del jugador objetivo (por ejemplo, después de comprobar que está esposado)
        Integrations[moduleType][moduleName].search = function(targetServerId)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Skillcheck">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/skillcheck`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `ox_lib`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "skillcheck"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Inicia un minijuego de skillcheck con la dificultad y velocidad indicadas
        Integrations[moduleType][moduleName].start = function(difficulty, speed)
            -- Añade tu código aquí
        end

        -- Cancela el minijuego de skillcheck que está en curso
        Integrations[moduleType][moduleName].cancel = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Stash">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/stash`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `jaksam_inventory`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "stash"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Abre la interfaz del stash para el marcador indicado
        Integrations[moduleType][moduleName].open = function(type, markerId)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `jobs_creator/_modules/textui`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `ox_lib`) y pégalo en la misma carpeta como plantilla.
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

        -- Muestra un mensaje de text UI con el texto indicado
        Integrations[moduleType][moduleName].show = function(message)
            -- Añade tu código aquí
        end

        -- Oculta el mensaje de text UI
        Integrations[moduleType][moduleName].hide = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
