---
title: "Get player armory weapons"
description: "Obtén la lista de armas que un jugador específico tiene almacenadas en una armería específica."
icon: "gun"
---

Obtén una lista de las armas de un jugador almacenadas en una ID de armería específica.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getPlayerArmoryWeapons(playerId, markerId)
```

```lua Example
local playerId = 20
local markerId = 52
local playerArmoryWeapons = exports["jobs_creator"]:getPlayerArmoryWeapons(playerId, markerId)
print("Player weapons in that armory")
print(ESX.DumpTable(playerArmoryWeapons))
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `markerId` | integer | La ID del marcador |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerArmoryWeapons` | table | Lista de todas las armas contenidas en el marcador depositadas por el jugador |
