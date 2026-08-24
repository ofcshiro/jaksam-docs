---
title: "Get all vehicles of player"
description: "Récupère tous les véhicules qu'un joueur possède dans l'ensemble des garages achetables."
icon: "car"
---

Récupère tous les véhicules possédés par un joueur (ID) dans l'ensemble des garages achetables.

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

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | ID serveur du joueur |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicles` | table | Table contenant tous les véhicules possédés par le joueur dans les garages achetables, la clé est l'ID du véhicule et la valeur est la donnée du véhicule |
