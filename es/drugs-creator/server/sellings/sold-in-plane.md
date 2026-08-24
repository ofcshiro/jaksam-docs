---
title: "Sold in plane"
description: "Se activa del lado del servidor después de que un jugador venda drogas estando en un avión."
icon: "plane"
---

Se activa después de que un jugador venda estando en un avión (por cada item vendido).

```lua Event
RegisterNetEvent("drugs_creator:plane:soldItem", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)

end)
```

### Parámetros

| Nombre              | Tipo de dato | Descripción                                                |
| ------------------ | --------- | -------------------------------------------------------------- |
| `playerId`          | integer   | ID de servidor del jugador                                                   |
| `drugName`          | string    | ID del item de la droga recién vendida                                        |
| `drugQuantity`      | integer   | Cantidad de item vendida                                                     |
| `totalDrugPrice`    | integer   | Dinero total que recibió el jugador                                    |
| `accountName`       | string    | Tipo de cuenta usada para la recompensa (money, black_money, etc.)               |

## Ejemplo

```lua
RegisterNetEvent("drugs_creator:plane:soldItem", function(playerId, drugName, drugQuantity, totalDrugPrice, accountName)
    local xPlayer = ESX.GetPlayerFromId(playerId)

    local random = math.random(1, 2)

    if(drugName == "weed" and random == 1) then
        xPlayer.addInventoryItem("weed", 3)

        xPlayer.showNotification("Here you have 3 bonus weed")
    end

    print("Player received " .. totalDrugPrice .. " in " .. accountName)
end)
```
