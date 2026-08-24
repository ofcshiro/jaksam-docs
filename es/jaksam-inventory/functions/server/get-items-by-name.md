---
title: "Get items by name"
description: "Obtiene todos los ítems de un inventario por nombre, con filtrado opcional por metadata."
icon: "tags"
---

Obtiene todos los ítems de un inventario por nombre, con filtrado opcional por metadata.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemsByName(inventoryId, itemName, metadata, strict)
```

```lua Example
-- Obtiene todos los panes en el inventario del jugador
local playerId = 1
local breads = exports['jaksam_inventory']:getItemsByName(playerId, 'bread')

print('Found ' .. #breads .. ' bread stacks')
for i = 1, #breads do
    local bread = breads[i]
    print('Slot ' .. bread.slot .. ': ' .. bread.amount .. ' breads')
end

-- Obtiene todas las armas con una metadata específica (ammo = 0)
local weapons = exports['jaksam_inventory']:getItemsByName(playerId, 'WEAPON_PISTOL', {
    ammo = 0
})

-- Calcula la cantidad total en todos los slots (se recomienda usar getTotalItemAmount en su lugar)
local totalBread = 0
local allBreads = exports['jaksam_inventory']:getItemsByName(playerId, 'bread')
for i = 1, #allBreads do
    totalBread = totalBread + allBreads[i].amount
end
print('Total bread amount:', totalBread)

-- Elimina todo el pan del inventario
local breads = exports['jaksam_inventory']:getItemsByName(playerId, 'bread')
for i = 1, #breads do
    exports['jaksam_inventory']:removeItem(playerId, 'bread', breads[i].amount, nil, breads[i].slot)
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario en el que buscar. Puede ser el ID de servidor de un jugador (number) o un ID de inventario (string) |
| `itemName` | string | El nombre de los ítems a buscar |
| `metadata` | table | Metadata con la que comparar al buscar. Si se proporciona, solo se devolverán los ítems con metadata coincidente |
| `strict` | boolean | Si se debe comparar la metadata de forma estricta (por defecto: nil). Si es true, todos los campos de metadata deben coincidir exactamente |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `items` | table | Array de todos los ítems encontrados que cumplen los criterios (cada uno con `name`, `amount`, `metadata`, `slot`). Tabla vacía `{}` si no se encuentra ningún ítem |

### Notas

- Cada ítem incluye el campo `slot` que indica dónde se encontró
- Usa esta función cuando necesites procesar varias pilas del mismo ítem
- Para búsquedas de un solo ítem, prefiere `getItemByName` por mejor rendimiento
