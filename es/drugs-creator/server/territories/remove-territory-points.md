---
title: "Remove territory points"
description: "Quita puntos a una facción en un territorio desde un script externo."
icon: "arrow-down"
---

Quita puntos a una facción en un territorio desde un script externo.

```lua Export
exports["drugs_creator"]:removeTerritoryPoints(territory, job, amount)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                                                |
| ------------- | --------- | -------------------------------------------------------------------------------- |
| `territory`    | string    | Nombre del territorio, o `"*"` para afectar a todos los territorios                                  |
| `job`          | string    | Nombre del job/gang al que quitar puntos, o `"*"` para afectar a todas las facciones configuradas       |
| `amount`       | integer   | Cantidad de puntos a quitar (debe ser > 0)                                                |

## Ejemplo

```lua
-- Quita 5 puntos a "vagos" en "RANCHO"
exports["drugs_creator"]:removeTerritoryPoints("RANCHO", "vagos", 5)
```
