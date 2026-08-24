---
title: "Item harvested"
description: "Déclenché côté serveur après qu'un item soit récolté dans un champ."
icon: "hand-holding"
---

Déclenché après qu'un item ait été récolté dans un champ.

```lua Event
RegisterNetEvent("drugs_creator:fields:itemHarvested", function(playerId, fieldId, itemName, itemQuantity)

end)
```

### Paramètres

| Nom             | Type de donnée | Description                             |
| ----------------- | --------- | -------------------------------------------- |
| `playerId`         | integer   | ID serveur du joueur                                 |
| `fieldId`          | integer   | ID du champ où l'item a été récolté              |
| `itemName`         | string    | ID de l'item qui vient d'être récolté                              |
| `itemQuantity`     | integer   | Quantité d'item récoltée                              |

## Exemple

```lua
-- Un exemple pour un système d'xp
RegisterNetEvent("drugs_creator:fields:itemHarvested", function(playerId, fieldId, itemName, itemQuantity)
    TriggerEvent("xp_system:addXp", playerId, itemName, itemQuantity)
end)
```
