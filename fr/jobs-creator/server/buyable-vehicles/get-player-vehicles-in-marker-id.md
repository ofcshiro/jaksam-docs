---
title: "Get player vehicles in marker ID"
description: "Récupère tous les véhicules qu'un joueur possède dans un marqueur de garage achetable donné."
icon: "car"
---

Récupère tous les véhicules possédés par un joueur (ID) dans un marqueur de garage achetable donné.

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

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | ID serveur du joueur |
| `markerId` | integer | ID du marqueur |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicles` | table | Table contenant tous les véhicules possédés par le joueur dans le garage, la clé est l'ID du véhicule et la valeur est la donnée du véhicule |
