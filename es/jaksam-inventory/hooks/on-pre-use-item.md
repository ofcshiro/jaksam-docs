---
title: "Pre use item"
description: "Hook activado antes de que se use un ítem, puede cancelar el uso."
icon: "hand"
---

Se activa ANTES de que se use un ítem (antes del consumo, animaciones y delays). Este hook puede cancelar el uso del ítem. Regístralo con [`registerHook`](/es/jaksam-inventory/hooks#registrar-un-hook) usando el nombre de event `onPreUseItem`.

**Orden de ejecución:** después de `STATIC_ITEM.canUse` y `oxServerExport 'usingItem'`, antes del consumo.

### Payload

| Campo | Tipo de Dato | Descripción |
| --- | --- | --- |
| `playerId` | number | El jugador que usa el ítem |
| `inventoryId` | string | p. ej. `"license:abcd1234"` |
| `slotId` | number | Slot del ítem que se está usando |
| `itemName` | string | p. ej. `"bread"` |
| `metadata` | table \| nil | Metadatos del ítem |

<Note>
  Este hook puede evitar el uso del ítem devolviendo `false`. Es útil para restricciones globales de uso de ítems (p. ej., jugadores esposados, restricciones en vehículos, restricciones de zona).
</Note>

### Ejemplos

<AccordionGroup>
  <Accordion title="Bloquear el uso de ítems cuando está esposado">
    ```lua
    exports['jaksam_inventory']:registerHook("onPreUseItem", function(payload)
        if IsPlayerHandcuffed(payload.playerId) then
            return false, "You cannot use items while handcuffed"
        end
    end)
    ```
  </Accordion>

  <Accordion title="Bloquear el uso de comida en vehículos">
    ```lua
    exports['jaksam_inventory']:registerHook("onPreUseItem", function(payload)
        local ped = GetPlayerPed(payload.playerId)
        if IsPedInAnyVehicle(ped, false) then
            return false, "You cannot eat while driving", "warning"
        end
    end, {
        itemTypeFilter = {food = true}
    })
    ```
  </Accordion>
</AccordionGroup>

Consulta [Descripción general de Hooks](/es/jaksam-inventory/hooks) para la API de `registerHook`, los filtros disponibles y el comportamiento de los valores de retorno.
