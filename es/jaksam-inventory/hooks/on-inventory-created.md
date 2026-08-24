---
title: "Inventory created"
description: "Hook activado cuando se crea un nuevo inventario, solo como notificación."
icon: "wand-magic-sparkles"
---

Se activa cuando se crea un nuevo inventario. Regístralo con [`registerHook`](/es/jaksam-inventory/hooks#registrar-un-hook) usando el nombre de event `onInventoryCreated`.

### Payload

| Campo | Tipo de Dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string | p. ej. `"stash_police"` |
| `inventoryType` | string | p. ej. `"stash"` |
| `label` | string | p. ej. `"Police Stash"` |
| `options` | table \| nil | Puede ser nil si no se configura explícitamente, en cuyo caso sigue la configuración de las opciones globales de inventario |
| `items` | table | Ítems en el inventario al momento de crearse |
| `metadata` | table | Metadatos adicionales del inventario |

<Note>
  Este hook es solo de notificación y no puede cancelar la creación del inventario. Es útil para agregar ítems iniciales, prepoblar inventarios con botín aleatorio, o registrar la creación de inventarios. Usa exports para agregar ítems al inventario dentro del callback.
</Note>

**Filtros disponibles:** `inventoryTypeFilter` (filtra por tipo de inventario: player, stash, trunk, dumpster, etc.), `inventoryFilter` (filtra por patrones específicos de ID de inventario).

### Ejemplos

<AccordionGroup>
  <Accordion title="Agregar ítems iniciales a nuevos inventarios de jugadores">
    ```lua
    exports['jaksam_inventory']:registerHook("onInventoryCreated", function(payload)
        exports["jaksam_inventory"]:addItem(payload.inventoryId, "bread", 5)
        exports["jaksam_inventory"]:addItem(payload.inventoryId, "water", 3)
        exports["jaksam_inventory"]:addItem(payload.inventoryId, "phone", 1)
    end, {
        inventoryTypeFilter = {player = true}
    })
    ```
  </Accordion>

  <Accordion title="Prepoblar contenedores de basura con botín aleatorio">
    <Note>
      Ya se incluye un hook existente para esto en la carpeta `_hooks` de jaksam_inventory.
    </Note>

    ```lua
    -- Tabla de botín: cada entrada tiene itemName, minAmount, maxAmount
    local lootTable = {
        {name = "trash", min = 1, max = 5},
        {name = "newspaper", min = 1, max = 2},
        {name = "bottle", min = 1, max = 3},
        {name = "sandwich", min = 1, max = 1},
        {name = "bandage", min = 1, max = 2},
    }

    -- Cantidad mínima y máxima de ítems diferentes por contenedor de basura
    local minItems, maxItems = 1, 3

    -- Barajado Fisher-Yates para selección aleatoria sin repetición
    local function shuffleTable(tbl)
        local shuffled = {}
        for i = 1, #tbl do shuffled[i] = tbl[i] end
        for i = #shuffled, 2, -1 do
            local j = math.random(1, i)
            shuffled[i], shuffled[j] = shuffled[j], shuffled[i]
        end
        return shuffled
    end

    exports['jaksam_inventory']:registerHook("onInventoryCreated", function(payload)
        local itemCount = math.random(minItems, math.min(maxItems, #lootTable))
        local shuffledLoot = shuffleTable(lootTable)

        for i = 1, itemCount do
            local loot = shuffledLoot[i]
            local amount = math.random(loot.min, loot.max)
            exports["jaksam_inventory"]:addItem(payload.inventoryId, loot.name, amount)
        end
    end, {
        inventoryTypeFilter = {dumpster = true}
    })
    ```
  </Accordion>
</AccordionGroup>

Consulta [Descripción general de Hooks](/es/jaksam-inventory/hooks) para la API de `registerHook`, los filtros disponibles y el comportamiento de los valores de retorno.
