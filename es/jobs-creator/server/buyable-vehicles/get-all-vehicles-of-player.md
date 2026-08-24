---
title: "Get all vehicles of player"
description: "Obtén todos los vehículos que un jugador posee en todos los garajes comprables."
icon: "car"
---

Obtén todos los vehículos que posee un ID de jugador en todos los garajes comprables.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getAllVehiclesOfPlayer(playerId)
```

```lua Example
local playerId = 4
local vehicles = exports["jobs_creator"]:getAllVehiclesOfPlayer(playerId)
print("Player vehicles:")
print(ESX.DumpTable(vehicles))
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicles` | table | Tabla con todos los vehículos que posee el jugador en los garajes comprables, la clave es la ID del vehículo y el valor son los datos del vehículo |
