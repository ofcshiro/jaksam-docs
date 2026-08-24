---
title: "Item processed"
description: "Se déclenche quand un joueur transforme un item à un marker de transformation."
icon: "gears"
---

Se déclenche quand un joueur transforme un item à un marker de transformation.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:process:processedItem", function(playerId, markerId, addedItemName, addedItemQuantity, removedItemName, removedItemQuantity)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:process:processedItem", function(playerId, markerId, addedItemName, addedItemQuantity, removedItemName, removedItemQuantity)
    TriggerEvent("xp_system:addExperience", playerId, "process")
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Server ID du joueur |
| `markerId` | integer | ID du marker |
| `addedItemName` | string | Nom de l'item reçu |
| `addedItemQuantity` | integer | Quantité de l'item reçu |
| `removedItemName` | string | Nom de l'item retiré |
| `removedItemQuantity` | integer | Quantité de l'item retiré |
