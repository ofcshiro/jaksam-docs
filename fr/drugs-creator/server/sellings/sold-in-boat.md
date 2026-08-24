---
title: "Sold in boat"
description: "Déclenché côté serveur après qu'un joueur vende des drogues en étant dans un bateau."
icon: "sailboat"
---

Déclenché après qu'un joueur vende en étant dans un bateau (pour chaque item vendu).

```lua Event
RegisterNetEvent("drugs_creator:boat:soldItem", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)

end)
```

### Paramètres

| Nom              | Type de donnée | Description                                                |
| ------------------ | --------- | -------------------------------------------------------------- |
| `playerId`          | integer   | ID serveur du joueur                                                   |
| `drugName`          | string    | ID de l'item de la drogue qui vient d'être vendue                                        |
| `drugQuantity`      | integer   | Quantité d'item vendue                                                     |
| `totalDrugPrice`    | integer   | Argent total reçu par le joueur                                    |
| `accountName`       | string    | Type de compte utilisé pour la récompense (money, black_money, etc.)               |

## Exemple

```lua
RegisterNetEvent("drugs_creator:boat:soldItem", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)
    local xPlayer = ESX.GetPlayerFromId(playerId)

    local random = math.random(1, 2)

    if(drugName == "weed" and random == 1) then
        xPlayer.addInventoryItem("weed", 3)

        xPlayer.showNotification("Here you have 3 bonus weed")
    end

    print("Player received " .. totalDrugPrice .. " in " .. accountName)
end)
```
