---
title: "Get player vehicles in marker ID"
description: "Obtén todos los vehículos que un jugador posee en un marcador de garaje comprable específico."
icon: "car"
---

Obtén todos los vehículos que posee un ID de jugador en un ID de marcador de garaje comprable específico.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getPlayerVehiclesInMarkerId(playerId, markerId)
```

```lua Example
local playerId = 1
local markerId = 252
local playerVehiclesInMarker = exports["jobs_creator"]:getPlayerVehiclesInMarkerId(playerId, markerId)
print(ESX.DumpTable(playerVehiclesInMarker))
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `markerId` | integer | ID del marcador |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicles` | table | Tabla con todos los vehículos que posee el jugador en el garaje, la clave es la ID del vehículo y el valor son los datos del vehículo |
