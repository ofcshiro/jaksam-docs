---
title: "Botones de Acción"
icon: "square-plus"
description: "Agrega botones personalizados siempre visibles a la barra de herramientas del inventario para menús, trabajos y acciones rápidas"
---

Los botones de acción son botones personalizados que aparecen en la barra de herramientas de la UI del inventario. A diferencia de las [Acciones de Contexto](/es/jaksam-inventory/guides/context-actions) (que aparecen al hacer clic derecho en un ítem), los botones de acción siempre están visibles en el encabezado del inventario y pueden activar cualquier lógica personalizada.

<Columns cols={2}>
  <Frame>
    ![Captura de pantalla de botones de acción](/images/action-buttons-1.jpg)
  </Frame>

  <Frame>
    ![Segunda captura de pantalla de botones de acción](/images/action-buttons-2.jpg)
  </Frame>
</Columns>

## Cuándo usar Botones de Acción

Usa botones de acción cuando necesites:

- Un botón siempre visible en el inventario (no específico de un ítem)
- Acceso rápido a funciones como "Menú de Policía", "Garaje", "Crafting", etc.
- Acciones específicas de un trabajo o rol

## Uso Básico

### Registrar un botón

```lua
exports['jaksam_inventory']:registerActionButton(
    'my_button',           -- ID único
    'bi-star-fill',        -- Clase de Bootstrap Icons
    'My Tooltip',          -- Tooltip al pasar el cursor (o nil)
    function()             -- Callback del clic
        print('Clicked!')
    end,
    true                   -- Visible (por defecto: true)
)
```

### Eliminar un botón

```lua
exports['jaksam_inventory']:unregisterActionButton('my_button')
```

### Mostrar/Ocultar sin eliminar

```lua
-- Ocultar (el botón sigue registrado, solo que invisible)
exports['jaksam_inventory']:hideActionButton('my_button')

-- Mostrar de nuevo
exports['jaksam_inventory']:showActionButton('my_button')
```

## Ejemplos Prácticos

<Tabs>
  <Tab title="Específico de un trabajo (Policía)">
    Registra el botón una vez cuando inicia el resource, y luego muéstralo/ocúltalo según el trabajo:

    ```lua
        -- Registrar al iniciar el resource (oculto por defecto)
        CreateThread(function()
            exports['jaksam_inventory']:registerActionButton(
                'police_menu',
                'bi-shield-check',
                'Police Actions',
                function()
                    TriggerEvent('police:openActionsMenu')
                end,
                false -- Empieza oculto
            )
        end)
    
        -- Mostrar/ocultar según cambios de trabajo
        AddEventHandler('esx:setJob', function(job)
            if job.name == 'police' then
                exports['jaksam_inventory']:showActionButton('police_menu')
            else
                exports['jaksam_inventory']:hideActionButton('police_menu')
            end
        end)
    
        -- También comprobar al cargar el jugador
        RegisterNetEvent('esx:playerLoaded', function(xPlayer)
            if xPlayer.job.name == 'police' then
                exports['jaksam_inventory']:showActionButton('police_menu')
            end
        end)
    ```
  </Tab>
  <Tab title="Abrir un stash">
    ```lua
        exports['jaksam_inventory']:registerActionButton(
            'open_personal_stash',
            'bi-box-seam',
            'Personal Stash',
            function()
                exports['jaksam_inventory']:openInventory('personal_stash_' .. GetPlayerServerId(PlayerId()))
            end
        )
    ```
  </Tab>
  <Tab title="Menú de crafting">
    ```lua
        exports['jaksam_inventory']:registerActionButton(
            'crafting_menu',
            'bi-hammer',
            'Crafting',
            function()
                TriggerEvent('crafting:openMenu')
            end
        )
    ```
  </Tab>
  <Tab title="Múltiples botones de trabajo">
    ```lua
        local jobButtons = {
            police = { id = 'btn_police', icon = 'bi-shield-check', tooltip = 'Police Menu', event = 'police:menu' },
            ambulance = { id = 'btn_ambulance', icon = 'bi-heart-pulse', tooltip = 'EMS Menu', event = 'ambulance:menu' },
            mechanic = { id = 'btn_mechanic', icon = 'bi-tools', tooltip = 'Mechanic Tools', event = 'mechanic:menu' },
        }
    
        -- Registrar todos los botones como ocultos
        CreateThread(function()
            for _, btn in pairs(jobButtons) do
                exports['jaksam_inventory']:registerActionButton(
                    btn.id,
                    btn.icon,
                    btn.tooltip,
                    function()
                        TriggerEvent(btn.event)
                    end,
                    false
                )
            end
        end)
    
        -- Mostrar el botón correcto según el trabajo
        AddEventHandler('esx:setJob', function(job)
            -- Ocultar todos los botones de trabajo
            for _, btn in pairs(jobButtons) do
                exports['jaksam_inventory']:hideActionButton(btn.id)
            end
    
            -- Mostrar el del trabajo actual (si existe)
            if jobButtons[job.name] then
                exports['jaksam_inventory']:showActionButton(jobButtons[job.name].id)
            end
        end)
    ```
  </Tab>
</Tabs>

## Notas Importantes

<CardGroup cols={1}>
  <Card title="IDs únicos" icon="fingerprint">
    Cada botón debe tener un ID único. Registrar con el mismo ID sobrescribirá el botón anterior.
  </Card>

  <Card title="Persistencia" icon="rotate">
    Los botones se mantienen al abrir/cerrar el inventario, pero se pierden al reiniciar el resource. Vuelve a registrarlos cuando tu resource inicie.
  </Card>

  <Card title="Rendimiento" icon="gauge-high">
    No registres/elimines botones repetidamente. Regístralos una vez y luego usa show/hide para alternar la visibilidad.
  </Card>
</CardGroup>
