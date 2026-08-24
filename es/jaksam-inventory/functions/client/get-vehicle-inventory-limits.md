---
title: "Get vehicle inventory limits"
description: "Devuelve los límites del maletero o la guantera de un vehículo según el modelo."
icon: "car"
---

Devuelve los límites del maletero o la guantera de un vehículo según el modelo. Usa la configuración de `_data/vehicles.lua` con prioridad: `trunkByModel`/`gloveboxByModel` > `trunkByClass`/`gloveboxByClass`. Devuelve `0, 0` si el vehículo/clase está configurado para no tener maletero/guantera (`noTrunkVehicles`, `noTrunkClasses`, etc.)

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getVehicleInventoryLimits(vehicleModel, inventoryType)
```

```lua Example
local vehicle = GetVehiclePedIsIn(PlayerPedId(), false)
local maxSlots, maxWeight = exports['jaksam_inventory']:getVehicleInventoryLimits(GetEntityModel(vehicle), "trunk")

if maxWeight then
    print("Trunk max weight: " .. maxWeight)
else
    print("No specific config for this vehicle model/class")
end

-- Obtiene los límites de la guantera para el vehículo 'adder'
local gloveboxSlots, gloveboxWeight = exports['jaksam_inventory']:getVehicleInventoryLimits('adder', "glovebox")
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicleModel` | number \| string | El hash del modelo del vehículo (de `GetEntityModel`) o el nombre del modelo como string |
| `inventoryType` | string | Puede ser `"trunk"` o `"glovebox"` |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `maxSlots` | number \| nil | El número máximo de slots del inventario del vehículo, o nil si no se encuentra configuración |
| `maxWeight` | number \| nil | El peso máximo del inventario del vehículo, o nil si no se encuentra configuración |

### Notas

En la documentación original faltaba una coma entre `'adder'` y `"glovebox"` en el ejemplo, corregida aquí. Vale la pena comprobar si ese también era un error en el propio script subyacente.
