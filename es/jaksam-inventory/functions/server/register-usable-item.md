---
title: "Register usable item"
description: "Registra una función de callback que se llamará cuando se use un ítem."
icon: "hand-pointer"
---

Registra una función de callback que se llamará cuando se use un ítem. El registro específico de cada framework seguirá funcionando igualmente, como `ESX.RegisterUsableItem` y su equivalente en QBCore.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:registerUsableItem(itemName, callback)
```

```lua Example: ESX
-- Registra un ítem usable en ESX
exports['jaksam_inventory']:registerUsableItem('bread', function(playerId, itemName, inventoryItem)
    -- Cura al jugador cuando se usa el pan
    local plyPed = GetPlayerPed(playerId)
    local health = GetEntityHealth(plyPed)
    SetEntityHealth(plyPed, math.min(health + 20, 200))
end)

-- Registra un ítem usable en ESX mostrando la metadata del ítem usado
exports['jaksam_inventory']:registerUsableItem('armour', function(playerId, itemName, inventoryItem)
    print("Armor has still " .. inventoryItem.metadata.value .. "% of durability")
end)
```

```lua Example: QBCore
-- Registra un ítem usable en QBCore
exports['jaksam_inventory']:registerUsableItem('armour', function(playerId, item)
    print("Armor has still " .. item.metadata.value .. "% of durability")
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre del ítem a registrar |
| `callback` | function | Función que se llama cuando se usa el ítem. Parámetros en ESX: `playerId, itemName, inventoryItem` (`name`, `metadata`, `amount`). Parámetros en QBCore: `playerId, inventoryItem` (`name`, `metadata`, `amount`, etc.) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si el registro se realizó correctamente |
