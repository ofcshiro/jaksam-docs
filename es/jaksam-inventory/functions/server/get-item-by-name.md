---
title: "Get item by name"
description: "Obtiene el primer ítem encontrado en un inventario por su nombre, con filtrado opcional por metadata."
icon: "tag"
---

Obtiene el primer ítem encontrado en un inventario por su nombre, con filtrado opcional por metadata.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemByName(inventoryId, itemName, metadata)
```

```lua Example
-- Obtiene el primer pan en el inventario del jugador
local playerId = 1
local item, slotId = exports['jaksam_inventory']:getItemByName(playerId, 'bread')

if item then
    print('Found bread in slot:', slotId)
    print('Amount in this slot:', item.amount)
    print('Item metadata:', json.encode(item.metadata))
end

-- Obtiene un arma con un número de serie específico
local weapon, weaponSlot = exports['jaksam_inventory']:getItemByName(playerId, 'WEAPON_PISTOL', {
    serial = "ABC123"
})

if weapon then
    print('Found weapon in slot:', weaponSlot)
    print('Weapon ammo:', weapon.metadata.ammo)
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario en el que buscar. Puede ser el ID de servidor de un jugador (number) o un ID de inventario (string) |
| `itemName` | string | El nombre del ítem a buscar |
| `metadata` | table | Metadata con la que comparar al buscar. Si se proporciona, solo se devolverán los ítems con metadata coincidente |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `item` | table \| nil | El primer ítem encontrado que cumple los criterios, o nil si no se encuentra |
| `slotId` | number \| nil | El ID de slot original donde se encontró el ítem (índice base 1), nil si no se encuentra el ítem |
