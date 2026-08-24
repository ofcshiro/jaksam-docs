---
title: "Get all armory weapons"
description: "Obtén la lista de todas las armas almacenadas en una armería específica."
icon: "gun"
---

Obtén una lista de todas las armas almacenadas en una ID de armería específica.

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

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `markerId` | integer | La ID del marcador |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `armoryWeapons` | table | Lista de todas las armas contenidas en el marcador |
