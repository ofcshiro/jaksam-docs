---
title: "Give territory points"
description: "Añade puntos a una facción en un territorio desde un script externo."
icon: "arrow-up"
---

Añade puntos a una facción en un territorio desde un script externo.

```lua Export
exports["drugs_creator"]:giveTerritoryPoints(territory, job, amount)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                                             |
| ------------- | --------- | ---------------------------------------------------------------------------- |
| `territory`    | string    | Nombre del territorio, o `"*"` para afectar a todos los territorios                              |
| `job`          | string    | Nombre del job/gang al que dar puntos, o `"*"` para afectar a todas las facciones configuradas       |
| `amount`       | integer   | Cantidad de puntos a añadir (debe ser > 0)                                              |

## Ejemplo

```lua
-- Da 2 puntos a "ballas" en "RANCHO"
exports["drugs_creator"]:giveTerritoryPoints("RANCHO", "ballas", 2)

-- Da 3 puntos a todas las facciones en todos los territorios
exports["drugs_creator"]:giveTerritoryPoints("*", "*", 3)
```
