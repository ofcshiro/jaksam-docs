---
title: "Get all armory weapons"
description: "Récupère la liste de toutes les armes stockées dans une armurerie donnée."
icon: "gun"
---

Récupère la liste de toutes les armes stockées dans une armurerie donnée via son ID.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getAllArmoryWeapons(markerId)
```

```lua Example
local markerId = 52
local allWeapons = exports["jobs_creator"]:getAllArmoryWeapons(markerId)
print("All players' weapons in that armory")
print(ESX.DumpTable(allWeapons))
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `markerId` | integer | L'ID du marqueur |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `armoryWeapons` | table | Liste de toutes les armes contenues dans le marqueur |
