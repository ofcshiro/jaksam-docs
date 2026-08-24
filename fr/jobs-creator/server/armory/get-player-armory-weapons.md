---
title: "Get player armory weapons"
description: "Récupère la liste des armes qu'un joueur donné a stockées dans une armurerie donnée."
icon: "gun"
---

Récupère la liste des armes d'un joueur stockées dans une armurerie donnée via son ID.

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

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | ID serveur du joueur |
| `markerId` | integer | L'ID du marqueur |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerArmoryWeapons` | table | Liste de toutes les armes contenues dans le marqueur et déposées par le joueur |
