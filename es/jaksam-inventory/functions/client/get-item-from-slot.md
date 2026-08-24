---
title: "Get item from slot"
description: "Obtiene un ítem de un slot específico en el inventario del jugador."
icon: "grid-2"
---

Obtiene un ítem de un slot específico en el inventario del jugador.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemFromSlot(slotId)
```

```lua Example
-- Obtiene el ítem del slot 5 del jugador
local item = exports['jaksam_inventory']:getItemFromSlot(5)

if item then
    print('Item name:', item.name)
    print('Amount:', item.amount)
    if item.metadata then
        print('Metadata:', json.encode(item.metadata))
    end
else
    print('Slot 5 is empty')
end

-- Comprueba si un slot específico tiene un arma
local slotItem = exports['jaksam_inventory']:getItemFromSlot(1)
if slotItem then
  local staticItem = exports['jaksam_inventory']:getStaticItem(slotItem.name)
  if staticItem and staticItem.type == 'weapon' then
    print('Found weapon in slot 1:', slotItem.name)
  end
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `slotId` | number | El número de slot del que obtener el ítem (en el inventario del jugador) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `item` | table \| nil | El ítem en el slot (`name`, `amount`, `metadata`), o nil si el slot está vacío |
