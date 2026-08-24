---
title: "Item removed"
description: "Hook activado cuando se elimina un ítem de un inventario."
icon: "circle-minus"
---

Se activa cuando se elimina un ítem de un inventario. Regístralo con [`registerHook`](/es/jaksam-inventory/hooks#registrar-un-hook) usando el nombre de event `onItemRemoved`.

### Payload

| Campo | Tipo de Dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string | p. ej. `"player:1"` |
| `itemName` | string | p. ej. `"bread"` |
| `amount` | number | Cantidad eliminada |
| `metadata` | table \| nil | Metadatos del ítem |
| `slotId` | number | Slot del que se eliminó el ítem |

<Info>
  [TODO: SE NECESITA INFORMACIÓN] El material fuente no incluía un ejemplo dedicado para este hook específico. Consulta [Descripción general de Hooks](/es/jaksam-inventory/hooks) para el patrón general de `registerHook` y los filtros, que se aplican de la misma manera aquí.
</Info>
