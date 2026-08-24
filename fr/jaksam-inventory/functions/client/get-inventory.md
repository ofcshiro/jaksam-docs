---
title: "Get inventory"
description: "Récupère l'inventaire personnel du joueur."
icon: "boxes-stacked"
---

Récupère l'inventaire personnel du joueur.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getInventory()
```

```lua Example
local inventory = exports['jaksam_inventory']:getInventory()

print(json.encode(inventory, {indent = true}))
--[[
{
    "id": "SIV35463",
    "limits": {
        "maxSlots": 20,
        "maxWeight": 30
    },
    "items": {
        "SLOT-3": {
            "name": "money",
            "amount": 4402
        },
        "SLOT-1": {
            "name": "weapon_advancedrifle",
            "metadata": {
                "serial": "TSK-24895-LFN"
            },
            "amount": 1
        },
    },
    "label": "Inventory",
    "totalWeight": 21.0,
}
]]
```

</CodeGroup>

### Paramètres

Aucun.

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventory` | table | L'inventaire personnel du joueur |
