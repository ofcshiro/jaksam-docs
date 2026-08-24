---
title: "Get items by name"
description: "Devuelve todos los ítems que coinciden con un nombre de ítem específico del inventario del jugador, incluyendo sus números de slot."
icon: "tags"
---

Devuelve todos los ítems que coinciden con un nombre de ítem específico del inventario del jugador. A diferencia de `getItemByName`, que devuelve solo la primera coincidencia, esta función devuelve todas las apariciones con sus números de slot.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemsByName(itemName)
```

```lua Example
-- Obtiene todos los ítems de pan en el inventario
local breadItems = exports['jaksam_inventory']:getItemsByName('bread')

print('Found ' .. #breadItems .. ' bread items')
for i, item in pairs(breadItems) do
    print('Slot ' .. item.slot .. ': ' .. item.amount .. 'x ' .. item.name)
end

-- Comprueba si el jugador tiene varias armas del mismo tipo
local pistols = exports['jaksam_inventory']:getItemsByName('weapon_pistol')
if #pistols > 1 then
    print('Player has multiple pistols in different slots')
    for i, pistol in pairs(pistols) do
        if pistol.metadata and pistol.metadata.serial then
            print('Serial: ' .. pistol.metadata.serial .. ' in slot ' .. pistol.slot)
        end
    end
end

-- Escenario sin ítems encontrados
local rareItems = exports['jaksam_inventory']:getItemsByName('rare_diamond')
if #rareItems == 0 then
    print('Player has no rare diamonds')
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre de los ítems a buscar en el inventario del jugador |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `items` | table | Array de todos los ítems que coinciden con el nombre. Cada ítem incluye `name`, `amount`, `metadata` y `slot`. Devuelve una tabla vacía si no se encuentra ningún ítem |
