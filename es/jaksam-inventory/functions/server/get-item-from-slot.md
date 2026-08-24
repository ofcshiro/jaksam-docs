---
title: "Get item from slot"
description: "Obtiene un ítem de un slot específico en un inventario."
icon: "grid-2"
---

Obtiene un ítem de un slot específico en un inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemFromSlot(inventoryId, slotId, returnRaw)
```

```lua Example
-- Obtiene el ítem del slot 5 del jugador
local playerId = 1
local item = exports['jaksam_inventory']:getItemFromSlot(playerId, 5)

if item then
    print('Item name:', item.name)
    print('Amount:', item.amount)
    print('Metadata:', json.encode(item.metadata))

    item.metadata.durability = 50 -- actualiza la metadata
    exports['jaksam_inventory']:setItemMetadataInSlot(playerId, 5, item.metadata) -- guarda la metadata
end

-- Obtiene un ítem de un stash
local stashItem = exports['jaksam_inventory']:getItemFromSlot('police_stash_1', 3)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario del que obtener el ítem. Puede ser el ID de servidor de un jugador (number) o un ID de inventario (string) |
| `slotId` | number | El número de slot del que obtener el ítem |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `item` | table \| nil | El ítem en el slot (`name`, `amount`, `metadata`), o nil si el slot está vacío |

### Notas

<Info>
  [TODO: INFORMATION NEEDED] La firma del export acepta un tercer parámetro `returnRaw` que no está documentado en el material fuente usado para esta página.
</Info>
