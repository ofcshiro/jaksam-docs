---
title: "Item sold"
description: "Se déclenche quand un joueur vend un item ou une arme à un marker de marché."
icon: "store"
---

Se déclenche quand un joueur vend un item/arme à un marker de marché.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:market:soldItem", function(playerId, markerId, itemName, itemQuantity, totalPrice)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:market:soldItem", function(playerId, markerId, itemName, itemQuantity, totalPrice)
    print("Player ID: " .. playerId .. " sold x" .. itemQuantity .. " " .. itemName .. " from shop " .. markerId)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Server ID du joueur |
| `markerId` | integer | ID du marker |
| `itemName` | string | Nom de l'item ou de l'arme |
| `itemQuantity` | integer | Quantité vendue |
| `totalPrice` | integer | Argent total reçu |
