---
title: "Item harvested"
description: "Déclenché côté serveur après qu'un item récoltable soit collecté."
icon: "hand-holding"
---

Déclenché après qu'un item récoltable ait été récolté.

```lua Event
RegisterNetEvent("drugs_creator:harvest:itemHarvested", function(playerId, itemName, itemQuantity)

end)
```

### Paramètres

| Nom             | Type de donnée | Description             |
| ----------------- | --------- | --------------------------- |
| `playerId`         | integer   | ID serveur du joueur                 |
| `itemName`         | string    | ID de l'item qui vient d'être récolté             |
| `itemQuantity`     | integer   | Quantité d'item récoltée             |

## Exemple

```lua
-- Un exemple pour un système d'xp
RegisterNetEvent("drugs_creator:harvest:itemHarvested", function(playerId, itemName, itemQuantity)
    TriggerEvent("xp_system:addXp", playerId, itemQuantity)
end)
```
