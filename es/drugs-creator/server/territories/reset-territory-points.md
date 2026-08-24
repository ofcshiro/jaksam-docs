---
title: "Reset territory points"
description: "Reinicia a 0 los puntos de una facción en un territorio."
icon: "rotate-left"
---

Reinicia los puntos de una facción en un territorio (los pone a 0). La propiedad se recalcula después del reinicio.

```lua Export
exports["drugs_creator"]:resetTerritoryPoints(territory, job)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                                          |
| ------------- | --------- | -------------------------------------------------------------------------- |
| `territory`    | string    | Nombre del territorio, o `"*"` para afectar a todos los territorios                            |
| `job`          | string    | Nombre del job/gang a reiniciar, o `"*"` para afectar a todas las facciones configuradas              |

## Ejemplo

```lua
-- Reinicia los puntos de "ballas" en "RANCHO"
exports["drugs_creator"]:resetTerritoryPoints("RANCHO", "ballas")

-- Reinicio completo: todas las facciones en todos los territorios
exports["drugs_creator"]:resetTerritoryPoints("*", "*")
```
