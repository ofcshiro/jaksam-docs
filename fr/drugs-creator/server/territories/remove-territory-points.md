---
title: "Remove territory points"
description: "Retire des points à une faction dans un territoire depuis un script externe."
icon: "arrow-down"
---

Retire des points à une faction dans un territoire depuis un script externe.

```lua Export
exports["drugs_creator"]:removeTerritoryPoints(territory, job, amount)
```

### Paramètres

| Nom         | Type de donnée | Description                                                                |
| ------------- | --------- | -------------------------------------------------------------------------------- |
| `territory`    | string    | Nom du territoire, ou `"*"` pour cibler tous les territoires                                  |
| `job`          | string    | Nom du job/gang à qui retirer des points, ou `"*"` pour cibler toutes les factions configurées       |
| `amount`       | integer   | Nombre de points à retirer (doit être > 0)                                                |

## Exemple

```lua
-- Retire 5 points aux "vagos" à "RANCHO"
exports["drugs_creator"]:removeTerritoryPoints("RANCHO", "vagos", 5)
```
