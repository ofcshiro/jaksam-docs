---
title: "Sold to NPC"
description: "Se déclenche côté serveur après une vente à un PNJ."
icon: "user"
---

Se déclenche après une vente à un PNJ.

```lua Event
RegisterNetEvent("drugs_creator:soldToNPC", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)

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
RegisterNetEvent("drugs_creator:soldToNPC", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)
    local xPlayer = ESX.GetPlayerFromId(playerId)

    local random = math.random(1, 2)

    if(drugName == "weed" and random == 1) then
        xPlayer.addInventoryItem("weed", 3)

        xPlayer.showNotification("Here you have 3 bonus weed")
    end

    print("Player received " .. totalDrugPrice .. " in " .. accountName)
end)
```
