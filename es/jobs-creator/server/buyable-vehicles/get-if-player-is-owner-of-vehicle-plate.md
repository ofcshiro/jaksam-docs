---
title: "Get if player is owner of vehicle plate"
description: "Comprueba si un jugador específico es el propietario de una matrícula de vehículo específica."
icon: "drivers-license"
---

Devuelve si un ID de jugador es el propietario de una matrícula específica.

<CodeGroup>

```lua Export
exports["jobs_creator"]:isPlayerOwnerOfVehiclePlate(playerId, plate)
```

```lua Example
local playerId = 1
local plate = "40PQB261"
local isTheVehicleOwner = exports["jobs_creator"]:isPlayerOwnerOfVehiclePlate(playerId, plate)
print("Is the player owner of that plate: " .. tostring(isTheVehicleOwner))
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `plate` | string | Matrícula del vehículo |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isOwner` | boolean | Si el jugador es el propietario del vehículo o no |
