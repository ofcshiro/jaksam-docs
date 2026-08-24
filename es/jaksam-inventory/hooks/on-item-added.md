---
title: "Item added"
description: "Hook activado cuando se agrega un ítem a un inventario."
icon: "circle-plus"
---

Se activa cuando se agrega un ítem a un inventario. Regístralo con [`registerHook`](/es/jaksam-inventory/hooks#registrar-un-hook) usando el nombre de event `onItemAdded`.

### Payload

| Campo | Tipo de Dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string | p. ej. `"player:1"` |
| `itemName` | string | p. ej. `"bread"` |
| `amount` | number | Cantidad agregada |
| `metadata` | table \| nil | Metadatos del ítem, puede ser nil |
| `slotId` | number | Slot al que se agregó el ítem |

### Ejemplos

<AccordionGroup>
  <Accordion title="Una mochila por jugador">
    ```lua
    exports['jaksam_inventory']:registerHook("onItemAdded", function(payload)
        local backpackCount = exports["jaksam_inventory"]:getTotalItemAmount(payload.inventoryId, "backpack")
        if backpackCount >= 1 then
            return false, "You can only have one backpack"
        end
    end, {
        itemNameFilter = {backpack = true},
        inventoryTypeFilter = {player = true}
    })
    ```
  </Accordion>

  <Accordion title="Filtrar por nombre de inventario específico">
    ```lua
    -- Solo activar cuando se agregan ítems al stash de policía
    exports['jaksam_inventory']:registerHook("onItemAdded", function(payload)
        print("Item added to police stash:", payload.itemName)
    end, {
        inventoryFilter = {"stash_police"}
    })
    ```
  </Accordion>
</AccordionGroup>

Consulta [Descripción general de Hooks](/es/jaksam-inventory/hooks) para la API de `registerHook`, los filtros disponibles y el comportamiento de los valores de retorno.
