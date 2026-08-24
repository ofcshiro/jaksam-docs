---
title: "Remove weapon from armory"
description: "Retire une arme d'un marqueur d'armurerie donné via son ID d'arme."
icon: "gun"
---

Retire une arme d'un marqueur ID pour un joueur donné.

<CodeGroup>

```lua Export
exports["jobs_creator"]:removeWeaponFromArmory(markerId, weaponId)
```

```lua Example
local markerId = 15
local weaponId = 356
local success = exports["jobs_creator"]:removeWeaponFromArmory(markerId, weaponId)
print(success)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `markerId` | integer | L'ID du marqueur |
| `weaponId` | integer | ID de l'arme dans la base de données, visible via `exports["jobs_creator"]:getAllArmoryWeapons(markerId)` |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isSuccessful` | boolean | Indique si l'arme a été retirée ou non |
