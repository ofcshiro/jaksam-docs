---
title: "Item processed"
description: "Se dispara cuando un jugador procesa un objeto en un marcador de procesamiento."
icon: "gears"
---

Se dispara cuando un jugador procesa un objeto en un marcador de procesamiento.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:process:processedItem", function(playerId, markerId, addedItemName, addedItemQuantity, removedItemName, removedItemQuantity)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:process:processedItem", function(playerId, markerId, addedItemName, addedItemQuantity, removedItemName, removedItemQuantity)
    TriggerEvent("xp_system:addExperience", playerId, "process")
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `markerId` | integer | ID del marcador |
| `addedItemName` | string | Nombre del objeto recibido |
| `addedItemQuantity` | integer | Cantidad del objeto recibido |
| `removedItemName` | string | Nombre del objeto eliminado |
| `removedItemQuantity` | integer | Cantidad del objeto eliminado |
