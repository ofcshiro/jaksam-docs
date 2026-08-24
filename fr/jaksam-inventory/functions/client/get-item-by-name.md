---
title: "Get item by name"
description: "Renvoie le premier item trouvé dans l'inventaire personnel du joueur par nom (l'ordre n'est pas garanti)."
icon: "tag"
---

Renvoie le premier item trouvé dans l'inventaire personnel du joueur par nom (l'ordre n'est pas garanti).

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

### Paramètres

Aucun.

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `item` | table | L'item trouvé dans l'inventaire personnel du joueur |
| `slotId` | number | L'ID du slot de l'item dans l'inventaire personnel du joueur |
