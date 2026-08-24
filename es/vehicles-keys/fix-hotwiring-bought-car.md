---
title: "Arreglar el puenteo de un coche comprado"
description: "Actualiza los vehículos propios de un jugador después de una compra para que no tenga que puentearlo, para los scripts de tienda de vehículos más comunes."
icon: "wrench"
---

## Script genérico

Si tienes que puentear un vehículo justo después de comprarlo, añade [esta simple línea de código](/es/vehicles-keys/client/refresh-self-owned-vehicles) a tu script, después de que el vehículo haya sido añadido a la tabla `owned_vehicles` / `player_vehicles` (dependiendo del framework).

Puede que quieras añadir un `Citizen.Wait(2000)` antes de esa línea, por si el vehículo todavía no estaba en la tabla en el momento en que activaste el evento.

## esx_vehicleshop

### Primer paso

Ve a `esx_vehicleshop/server/main.lua` y busca el siguiente código:

<Frame>
  ![esx_vehicleshop setVehicleOwnedPlayerId before](/images/esx_vehicleshop_setVehicleOwnedPlayerId_before.png)
</Frame>

Y añade esta línea:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(playerId)
```

<Frame>
  ![esx_vehicleshop setVehicleOwnedPlayerId after](/images/esx_vehicleshop_setVehicleOwnedPlayerId_after.png)
</Frame>

### Segundo paso

Ve a `esx_vehicleshop/server/main.lua` (el mismo archivo que antes) y busca el siguiente código:

<Frame>
  ![esx_vehicleshop buyVehicle before](/images/esx_vehicleshop_buyVehicle_before.png)
</Frame>

Y añade esta línea:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(source)
```

<Frame>
  ![esx_vehicleshop buyVehicle after](/images/esx_vehicleshop_buyVehicle_after.png)
</Frame>

## esx_advancedvehicleshop

Ve a `esx_advancedvehicleshop/server/main.lua` y busca el siguiente código:

<Frame>
  ![esx_advancedvehicleshop before](/images/esx_advancedvehicleshop_before.png)
</Frame>

Y añade esta línea:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(source)
```

<Frame>
  ![esx_advancedvehicleshop after](/images/esx_advancedvehicleshop_after.png)
</Frame>

## qb-vehicleshop

### Primer paso

Ve a `qb-vehicleshop/server.lua` y añade el siguiente código después de **todas** las llamadas a `exports.oxmysql:insert`.

<Note>
  En el ejemplo se muestra solo una vez, pero tienes que añadirlo varias veces.
</Note>

<Frame>
  ![qb-vehicleshop before](/images/qb-vehicleshop_before.png)
</Frame>

Añade el siguiente código:

```lua
SetTimeout(1000, function()
    exports["vehicles_keys"]:refreshPlayerOwnedVehicles( pData.PlayerData.source )
end)
```

En ciertas partes, tendrás que reemplazar `pData` por otra cosa. Aquí se muestra dónde añadir el código y de qué depende `pData`.

<Frame>
  ![qb-vehicleshop after](/images/qb-vehicleshop_after.png)
</Frame>

<Note>
  Los círculos verdes que se muestran en la captura deben coincidir — así que si el primero es, por ejemplo, `targetPlayer`, el segundo también debe ser `targetPlayer`.
</Note>

### Segundo paso

Ve a `qb-vehicleshop/server.lua` (el mismo archivo que antes) y reemplaza todos estos eventos (están al final del archivo):

```lua
TriggerClientEvent('vehiclekeys:client:SetOwner', buyerId, plate)
```

por el siguiente código:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(buyerId)
```

## okokVehicleShop

Ve a `okokVehicleShop/sv_utils.lua` y busca el siguiente código:

<Frame>
  ![okokVehicleShop before](/images/okokVehicleShop_before.png)
</Frame>

Y añade esta línea:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(_source)
```

<Frame>
  ![okokVehicleShop after](/images/okokVehicleShop_after.png)
</Frame>

## s4-vehicleshop

Ve a `s4-vehicleshop/server.lua` y busca el siguiente código:

<Frame>
  ![s4-vehicleshop before](/images/s4-vehicleshop_before.png)
</Frame>

Y añade el siguiente código:

```lua
SetTimeout(1000, function()
    exports["vehicles_keys"]:refreshPlayerOwnedVehicles(src)
end)
```

<Frame>
  ![s4-vehicleshop after](/images/s4-vehicleshop_after.png)
</Frame>

<Note>
  Este código funciona tanto para la versión de _oxmysql_ como para la de _ghmattimysql_.
</Note>

## t1ger_dealerships

### Primer paso

Ve a `t1ger_dealerships/server/main.lua` y añade la siguiente línea debajo de **todas** las apariciones (más de una) del código mostrado en el ejemplo:

```lua
exports['t1ger_keys']:UpdateKeysToDatabase(props.plate, true)
```

<Frame>
  ![t1ger_dealerships before](/images/t1ger_dealerships_before.png)
</Frame>

Añade la siguiente línea:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(xPlayer.source)
```

<Frame>
  ![t1ger_dealerships after](/images/t1ger_dealerships_after.png)
</Frame>

### Segundo paso

Ve a `t1ger_dealerships/server/main.lua` (el mismo archivo que antes) y busca el siguiente código:

<Frame>
  ![t1ger_dealerships2 before](/images/t1ger_dealerships2_before.png)
</Frame>

Añade la siguiente línea:

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(xPlayer.source)
```

<Frame>
  ![t1ger_dealerships2 after](/images/t1ger_dealerships2_after.png)
</Frame>
