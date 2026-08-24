---
title: "Módulos"
description: "Reemplaza funciones por defecto como notify, la barra de progreso, el stash y los logs con tus propios módulos personalizados."
icon: "puzzle-piece"
---

Los módulos son una forma sencilla de que Drugs Creator reemplace ciertas funciones por defecto (notify, barra de progreso, stash, logs).

Para elegir un módulo existente, abre el menú `/drugscreator`, ve a la configuración y selecciónalo. Así de fácil.

### Módulos disponibles

| Categoría | Opciones disponibles |
| --- | --- |
| Dispatch | `codesign`, `default`, `rcore`, `roadphone` |
| Gangs | `default` |
| Inventory | `jaksam_inventory`, `ox_inventory`, `qb-inventory` |
| Logs | `custom`, `jaksam` |
| Menu | `menu_default`, `ox_context`, `ox_lib` |
| Progress Bar | `jaksam`, `ox_lib`, `qb-core` |
| Stash | `jaksam_inventory`, `ox-inventory`, `qb-inventory` |
| Text UI | `esx`, `none`, `ox_lib` |

### Crear un módulo personalizado

Elige la categoría para la que quieres crear un módulo. Cada pestaña te guía paso a paso para esa categoría y te da una plantilla lista para editar.

<Tabs>
  <Tab title="Dispatch">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/dispatch`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "dispatch"
        local moduleName = "yourModuleName" -- Renombra para que coincida con la integración que estás creando

        -- No lo toques, es necesario para que aparezca en la configuración ingame
        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Se ejecuta una vez por llamada, del lado del servidor
        Integrations[moduleType][moduleName].alertPoliceServerSide = function(coords, message, category)
            if not IsDuplicityVersion() then return end

            -- Añade tu código aquí (por ejemplo, llama al export/event de tu script de dispatch para alertar a la policía)
        end

        -- Se ejecuta del lado del cliente, en el cliente de cada agente de policía
        Integrations[moduleType][moduleName].alertPoliceMemberClientSide = function(coords, message, category)
            if IsDuplicityVersion() then return end

            -- Añade tu código aquí (por ejemplo, muestra un blip/notificación al agente)
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Gangs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/gangs`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "gangs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        --- Comprueba si un jugador tiene permiso de gang según su gang y nivel de grado, DEL LADO DEL SERVIDOR
        --- @param playerId number - El ID de servidor del jugador
        --- @param allowedGangs table<string, boolean|table<string, boolean>> - Tabla de gangs permitidas y sus grados
        --- @return boolean|nil - Si el jugador tiene permiso
        Integrations[moduleType][moduleName].isPlayerGangAllowed = function(playerId, allowedGangs)
            -- Añade tu código aquí
        end

        --- La misma comprobación, pero DEL LADO DEL CLIENTE
        --- @param allowedGangs table<string, boolean|table<string, boolean>>
        --- @return boolean|nil
        Integrations[moduleType][moduleName].isClientGangAllowed = function(allowedGangs)
            -- Añade tu código aquí
        end

        --- Devuelve el nombre de la gang de un jugador, DEL LADO DEL SERVIDOR
        --- @param playerId number
        --- @return string|nil
        Integrations[moduleType][moduleName].getPlayerGangName = function(playerId)
            -- Añade tu código aquí
        end

        --- Devuelve el nombre de la gang del jugador local, DEL LADO DEL CLIENTE
        --- @return string|nil
        Integrations[moduleType][moduleName].getClientGangName = function()
            -- Añade tu código aquí
        end

        --- Devuelve todas las gangs disponibles en el juego
        --- @return table<string, { label: string, grades: table<number, { grade: number, label: string }> }>
        Integrations[moduleType][moduleName].getAllGangs = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Inventory">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/inventory`.
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
        local moduleType = "inventory"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Devuelve el ID del slot que contiene el item indicado, o nil si no hay ninguno
        Integrations[moduleType][moduleName].getSlotIdWithItem = function(playerId, itemName, metadata)
            -- Añade tu código aquí
        end

        -- Establece metadata en el item del slot indicado
        Integrations[moduleType][moduleName].setItemMetadata = function(playerId, slotId, metadata)
            -- Añade tu código aquí
        end

        -- Devuelve los datos del item almacenado en el slot indicado
        Integrations[moduleType][moduleName].getSlotItem = function(playerId, slotId)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/logs`.
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

  <Tab title="Menu">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/menu`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `menu_default`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado y edítalo para que coincida con los events del script de terceros que estás integrando:

        ```lua
        local moduleType = "menu"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Abre un menú con los elementos indicados
        Integrations[moduleType][moduleName].open = function(id, title, elements, onSelect, onClose)
            -- Añade tu código aquí
        end

        -- Cierra cualquier menú abierto por este módulo
        Integrations[moduleType][moduleName].closeAll = function()
            -- Añade tu código aquí
        end

        -- Pide al jugador un número entre min y max
        Integrations[moduleType][moduleName].askQuantity = function(title, min, max)
            -- Añade tu código aquí
        end

        -- Pide al jugador un texto libre
        Integrations[moduleType][moduleName].askInput = function(title)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Progress Bar">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/progressbar`.
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

  <Tab title="Stash">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/stash`.
      </Step>
      <Step title="Duplica un módulo existente">
        Copia un módulo existente (por ejemplo `jaksam_inventory`) y pégalo en la misma carpeta como plantilla.
      </Step>
      <Step title="Renombra la copia">
        Renombra la copia pegada para que coincida con la integración que quieres crear.
      </Step>
      <Step title="Implementa las funciones necesarias">
        Abre el archivo renombrado (del lado del cliente y del servidor) y edítalo para que coincida con los events del script de terceros que estás integrando:

        Cliente:
        ```lua
        local moduleType = "stash"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Abre la UI del stash para el jugador
        Integrations[moduleType][moduleName].open = function(stashId)
            -- Añade tu código aquí
        end
        ```
        Servidor:
        ```lua
        -- Registra el stash para que exista y pueda abrirse
        Integrations[moduleType][moduleName].register = function(options)
            -- Añade tu código aquí
        end

        -- Añade un item al stash
        Integrations[moduleType][moduleName].addItem = function(stashId, itemName, amount, metadata)
            -- Añade tu código aquí
        end

        -- Elimina un item del stash
        Integrations[moduleType][moduleName].removeItem = function(stashId, itemName, amount, metadata)
            -- Añade tu código aquí
        end

        -- Devuelve cuántos itemName hay actualmente en el stash
        Integrations[moduleType][moduleName].getItemCount = function(stashId, itemName)
            -- Añade tu código aquí
        end

        -- Devuelve si cabría amount más de itemName en el stash
        Integrations[moduleType][moduleName].canAddItem = function(stashId, itemName, amount)
            -- Añade tu código aquí
        end

        -- Elimina todos los items del stash
        Integrations[moduleType][moduleName].clearStash = function(stashId)
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Ve a la carpeta de módulos">
        Ve a la carpeta `drugs_creator/_modules/textui`.
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

        -- Muestra un aviso de texto en pantalla con el mensaje indicado
        Integrations[moduleType][moduleName].show = function(message)
            -- Añade tu código aquí
        end

        -- Oculta el aviso de texto en pantalla
        Integrations[moduleType][moduleName].hide = function()
            -- Añade tu código aquí
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
