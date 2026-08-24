---
title: "Item crafted"
description: "Se déclenche quand un joueur fabrique un item à un marker de table de craft."
icon: "hammer"
---

Se déclenche quand un joueur fabrique un item à un marker de table de craft.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:crafting_table:craftedItem", function(playerId, markerId, itemName, itemQuantity)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:crafting_table:craftedItem", function(playerId, markerId, itemName, itemQuantity)
    TriggerEvent("xp_system:addExperience", playerId, "craft")
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Server ID du joueur |
| `markerId` | integer | ID du marker |
| `itemName` | string | Nom de l'item fabriqué |
| `itemQuantity` | integer | Quantité fabriquée |
