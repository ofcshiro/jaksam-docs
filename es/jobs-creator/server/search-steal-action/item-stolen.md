---
title: "Item Stolen"
description: "Se dispara después de que un jugador roba algo desde el menú de acciones, solo si usas el registro/robo de jugadores por defecto, no funcionará si lo reemplazaste"
icon: "hand"
---

Se dispara después de que un jugador roba algo desde el menú de acciones.

<Note>
  Esto solo funciona si usas la acción de registro/robo de jugadores por defecto — no se disparará si la reemplazaste por un módulo personalizado.
</Note>

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:itemStolen", function(playerId, targetId, itemName, itemQuantity)
end)
```

```lua Example
-- Este ejemplo para ESX "eliminará" todos los objetos robados
RegisterNetEvent("jobs_creator:actions:itemStolen", function(playerId, targetId, itemName, itemQuantity)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    xPlayer.removeInventoryItem(itemName, itemQuantity)
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | La ID de servidor del jugador que robó el objeto |
| `targetId` | integer | La ID de servidor de la víctima que perdió el objeto |
| `itemName` | string | Nombre del objeto |
| `itemQuantity` | integer | Cantidad robada |
