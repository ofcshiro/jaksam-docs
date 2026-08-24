---
title: "Get inventory ID from plate"
description: "Resuelve el ID completo del inventario de un compartimento del vehículo usando solo la matrícula."
icon: "id-card"
---

Resuelve el ID completo del inventario de un compartimento del vehículo usando solo la matrícula.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getInventoryIdFromPlate(plate, compartment)
```

```lua Example
-- Obtiene el ID del inventario del maletero
local plate = GetVehicleNumberPlateText(vehicle)
local trunkId = exports['jaksam_inventory']:getInventoryIdFromPlate(plate, "trunk")

if trunkId then
    print("Trunk ID: " .. trunkId)
    -- Ahora puedes usar las funciones estándar de inventario
    local inventory = exports['jaksam_inventory']:getInventory(trunkId)
end

-- Obtiene el ID del inventario de la guantera
local gloveboxId = exports['jaksam_inventory']:getInventoryIdFromPlate("ABC 123", "glovebox")
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `plate` | string | La matrícula del vehículo |
| `compartment` | string | Puede ser "trunk" o "glovebox" |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| nil | El ID completo del inventario (formato: `"vehicle:plate:model:compartment"`), nil si no se encuentra el vehículo |

### Notas

Busca en este orden:

1. Base de datos de vehículos propios (ESX: `owned_vehicles`, QBCore: `player_vehicles`)
2. Inventarios existentes en la tabla `jaksam_inventory`
3. Vehículos actualmente generados (`GetAllVehicles` - vehículos de NPC)

Para vehículos propios, crea automáticamente el inventario si no existe. Los inventarios creados son persistentes para vehículos propios y temporales para vehículos de NPC. Funciona incluso si el vehículo no está actualmente generado (garaje).
