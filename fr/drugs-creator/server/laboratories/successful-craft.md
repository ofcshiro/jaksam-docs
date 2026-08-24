---
title: "Successful craft"
description: "Déclenché côté serveur après un craft réussi dans un laboratoire."
icon: "flask-round-potion"
---

Déclenché après un craft réussi dans un laboratoire.

```lua Event
RegisterNetEvent("drugs_creator:laboratory:successfulCraft", function(playerId, ingredientsUsed, itemsToGive, laboratoryId)

end)
```

### Paramètres

| Nom                | Type de donnée     | Description                                                                                                    |
| -------------------- | -------------- | -------------------------------------------------------------------------------------------------------------- |
| `playerId`            | integer         | ID serveur du joueur                                                                                                    |
| `ingredientsUsed`     | table           | Table contenant les ingrédients utilisés. Clé = nom de l'ingrédient, Valeur = quantité de l'ingrédient                            |
| `itemsToGive`         | table/array     | Un tableau de tables représentant les items à donner. Chaque table a les propriétés `itemName` et `itemQuantity`            |
| `laboratoryId`        | integer         | ID du laboratoire                                                                                                        |

## Exemple

```lua
-- Un exemple pour un système d'xp
RegisterNetEvent("drugs_creator:laboratory:successfulCraft", function(playerId, ingredientsUsed, itemsToGive, laboratoryId)
    for k, resultItem in pairs(itemsToGive) do
        local itemName = resultItem.itemName
        local quantity = resultItem.itemQuantity

        TriggerEvent("xp_system:addXp", playerId, quantity)
    end
end)
```
