---
title: "Give territory points"
description: "Ajoute des points à une faction dans un territoire depuis un script externe."
icon: "arrow-up"
---

Ajoute des points à une faction dans un territoire depuis un script externe.

```lua Export
exports["drugs_creator"]:giveTerritoryPoints(territory, job, amount)
```

### Paramètres

| Nom         | Type de donnée | Description                                                             |
| ------------- | --------- | ---------------------------------------------------------------------------- |
| `territory`    | string    | Nom du territoire, ou `"*"` pour cibler tous les territoires                              |
| `job`          | string    | Nom du job/gang à qui donner des points, ou `"*"` pour cibler toutes les factions configurées       |
| `amount`       | integer   | Nombre de points à ajouter (doit être > 0)                                              |

## Exemple

```lua
-- Donne 2 points aux "ballas" à "RANCHO"
exports["drugs_creator"]:giveTerritoryPoints("RANCHO", "ballas", 2)

-- Donne 3 points à toutes les factions dans tous les territoires
exports["drugs_creator"]:giveTerritoryPoints("*", "*", 3)
```
