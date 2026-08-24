---
title: "Add weapon to armory"
description: "Ajoute une arme à un marqueur d'armurerie donné pour un joueur donné."
icon: "gun"
---

Ajoute une arme à un marqueur ID pour un joueur donné.

<CodeGroup>

```lua Export
exports["jobs_creator"]:addWeaponToArmory(markerId, playerIdentifier, weaponName, weaponAmmo, weaponComponents, weaponTintIndex)
```

```lua Example
local success = exports["jobs_creator"]:addWeaponToArmory(3, "2570e6efd3671584d7ed05a45cbf4156f782wwac", "WEAPON_PISTOL", 5, {}, 1)
print(success)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `markerId` | integer | L'ID du marqueur |
| `playerIdentifier` | string | Identifiant du joueur |
| `weaponName` | string | Nom de l'arme |
| `weaponAmmo` | integer | Quantité de munitions |
| `weaponComponents` | table | Table des composants de l'arme |
| `weaponTintIndex` | integer | Index de teinte de l'arme |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isSuccessful` | boolean | Indique si l'arme a été ajoutée ou non |
