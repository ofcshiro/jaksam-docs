---
title: "Get static items list"
description: "Devuelve la lista de todos los ítems del inventario."
icon: "list"
---

Devuelve la lista de todos los ítems del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getStaticItemsList()
```

```lua Example
local items = exports['jaksam_inventory']:getStaticItemsList()
local weaponsCount = 0
for itemName, item in pairs(items) do
    if item.type == 'weapon' then
        weaponsCount = weaponsCount + 1
    end
end
print("There are in total " .. weaponsCount .. " registered weapons in the inventory")
```

</CodeGroup>

### Parámetros

Ninguno.

### Valor de retorno

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `items` | table | La lista de ítems, la clave es el nombre del ítem, el valor es la información del ítem (label, maxStack, weight, stackable, description, rarity, type, etc.) |
