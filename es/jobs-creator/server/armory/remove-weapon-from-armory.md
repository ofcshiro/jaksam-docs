---
title: "Remove weapon from armory"
description: "Elimina un arma de un marcador de armería específico mediante su ID de arma."
icon: "gun"
---

Elimina un arma de una ID de marcador para un jugador específico.

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

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `markerId` | integer | La ID del marcador |
| `weaponId` | integer | ID del arma en la base de datos, se puede consultar en `exports["jobs_creator"]:getAllArmoryWeapons(markerId)` |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isSuccessful` | boolean | Si el arma fue eliminada o no |
