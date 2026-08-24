---
title: "Get item by name"
description: "Devuelve el primer ítem encontrado en el inventario propio del jugador por nombre (el orden no está garantizado)."
icon: "tag"
---

Devuelve el primer ítem encontrado en el inventario propio del jugador por nombre (el orden no está garantizado).

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemByName(itemName)
```

```lua Example
local item, slotId = exports['jaksam_inventory']:getItemByName('weapon_advancedrifle')

print(json.encode(item, {indent = true}), "SLOT ID: " .. slotId)
--[[
{
    "name": "weapon_advancedrifle",
    "metadata": {
        "serial": "TSK-24895-LFN"
    },
    "amount": 1
}
SLOT ID: 1
]]
```

</CodeGroup>

### Parámetros

Ninguno.

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `item` | table | El ítem encontrado en el inventario propio del jugador |
| `slotId` | number | El ID del slot del ítem en el inventario propio del jugador |
