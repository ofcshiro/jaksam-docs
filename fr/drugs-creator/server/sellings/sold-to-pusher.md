---
title: "Sold to pusher"
description: "Se déclenche côté serveur après qu'un joueur vend de la drogue à un pusher."
icon: "user"
---

Se déclenche après qu'un joueur vend à un pusher.

```lua Event
RegisterNetEvent("drugs_creator:pushers:itemSold", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)

end)
```

### Paramètres

| Nom              | Type de donnée | Description                                                |
| ------------------ | --------- | -------------------------------------------------------------- |
| `playerId`          | integer   | Server ID du joueur                                                   |
| `drugName`          | string    | ID de l'item de la drogue vendue                                        |
| `drugQuantity`      | integer   | Quantité de l'item vendue                                                     |
| `totalDrugPrice`    | integer   | Argent total reçu par le joueur                                    |
| `accountName`       | string    | Type de compte utilisé pour la récompense (money, black_money, etc.)               |

## Exemple

```lua
RegisterNetEvent("drugs_creator:pushers:itemSold", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)
    local xPlayer = ESX.GetPlayerFromId(playerId)

    local random = math.random(1, 2)

    if(drugName == "weed" and random == 1) then
        xPlayer.addInventoryItem("weed", 3)

        xPlayer.showNotification("Here you have 3 bonus weed")
    end

    print("Player received " .. totalDrugPrice .. " in " .. accountName)
end)
```
