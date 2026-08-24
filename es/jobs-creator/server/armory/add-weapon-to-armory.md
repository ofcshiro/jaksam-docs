---
title: "Add weapon to armory"
description: "Añade un arma a un marcador de armería específico para un jugador determinado."
icon: "gun"
---

Añade un arma a una ID de marcador para un jugador específico.

<CodeGroup>

```lua Export
exports["jobs_creator"]:addWeaponToArmory(markerId, playerIdentifier, weaponName, weaponAmmo, weaponComponents, weaponTintIndex)
```

```lua Example
local success = exports["jobs_creator"]:addWeaponToArmory(3, "2570e6efd3671584d7ed05a45cbf4156f782wwac", "WEAPON_PISTOL", 5, {}, 1)
print(success)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `markerId` | integer | La ID del marcador |
| `playerIdentifier` | string | Identificador del jugador |
| `weaponName` | string | Nombre del arma |
| `weaponAmmo` | integer | Cantidad de munición |
| `weaponComponents` | table | Tabla de componentes del arma |
| `weaponTintIndex` | integer | Índice de tinte del arma |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isSuccessful` | boolean | Si el arma fue añadida o no |
