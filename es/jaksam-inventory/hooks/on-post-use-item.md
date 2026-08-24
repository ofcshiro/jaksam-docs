---
title: "Post use item"
description: "Hook activado después de que se ha usado un ítem, solo como notificación."
icon: "circle-check"
---

Se activa DESPUÉS de que se ha usado un ítem (después del consumo, animaciones, delays y todos los callbacks). Regístralo con [`registerHook`](/es/jaksam-inventory/hooks#registrar-un-hook) usando el nombre de event `onPostUseItem`.

**Orden de ejecución:** al final del proceso de uso del ítem, después de `oxServerExport 'usedItem'`.

### Payload

| Campo | Tipo de Dato | Descripción |
| --- | --- | --- |
| `playerId` | number | El jugador que usó el ítem |
| `inventoryId` | string | p. ej. `"license:abcd1234"` |
| `slotId` | number | Slot del ítem que se usó |
| `itemName` | string | p. ej. `"bread"` |
| `metadata` | table \| nil | Metadatos del ítem |

<Note>
  Este hook es solo de notificación y no puede cancelar el uso del ítem. Es útil para registros, estadísticas, logros y activar sistemas externos.
</Note>

### Ejemplos

<AccordionGroup>
  <Accordion title="Registrar todo el uso de ítems">
    ```lua
    exports['jaksam_inventory']:registerHook("onPostUseItem", function(payload)
        print(("Player %d used %s"):format(payload.playerId, payload.itemName))
        -- Enviar a un sistema de registro externo, base de datos, etc.
    end)
    ```
  </Accordion>

  <Accordion title="Registrar estadísticas de consumo de comida">
    ```lua
    local foodStats = {}

    exports['jaksam_inventory']:registerHook("onPostUseItem", function(payload)
        foodStats[payload.itemName] = (foodStats[payload.itemName] or 0) + 1
        print("Total", payload.itemName, "consumed:", foodStats[payload.itemName])
    end, {
        itemTypeFilter = {food = true}
    })
    ```
  </Accordion>
</AccordionGroup>

Consulta [Descripción general de Hooks](/es/jaksam-inventory/hooks) para la API de `registerHook`, los filtros disponibles y el comportamiento de los valores de retorno.
