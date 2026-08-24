---
title: "Item sold"
description: "Se dispara cuando un jugador vende un objeto o arma en un marcador de mercado."
icon: "store"
---

Se dispara cuando un jugador vende un objeto/arma en un marcador de mercado.

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

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `markerId` | integer | ID del marcador |
| `itemName` | string | Nombre del objeto o arma |
| `itemQuantity` | integer | Cantidad vendida |
| `totalPrice` | integer | Dinero total recibido |
