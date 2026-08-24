---
title: "Item crafted"
description: "Se dispara cuando un jugador crea un objeto en un marcador de mesa de crafting."
icon: "hammer"
---

Se dispara cuando un jugador crea un objeto en un marcador de mesa de crafting.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:crafting_table:craftedItem", function(playerId, markerId, itemName, itemQuantity)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:crafting_table:craftedItem", function(playerId, markerId, itemName, itemQuantity)
    TriggerEvent("xp_system:addExperience", playerId, "craft")
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `markerId` | integer | ID del marcador |
| `itemName` | string | Nombre del objeto creado |
| `itemQuantity` | integer | Cantidad del objeto creado |
