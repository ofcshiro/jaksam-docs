---
title: "Reset territory points"
description: "Remet à 0 les points d'une faction dans un territoire."
icon: "rotate-left"
---

Remet à 0 les points d'une faction dans un territoire. La possession est recalculée après la réinitialisation.

```lua Export
exports["drugs_creator"]:resetTerritoryPoints(territory, job)
```

### Paramètres

| Nom         | Type de donnée | Description                                                          |
| ------------- | --------- | -------------------------------------------------------------------------- |
| `territory`    | string    | Nom du territoire, ou `"*"` pour cibler tous les territoires                            |
| `job`          | string    | Nom du job/gang à réinitialiser, ou `"*"` pour cibler toutes les factions configurées              |

## Exemple

```lua
-- Réinitialise les points des "ballas" à "RANCHO"
exports["drugs_creator"]:resetTerritoryPoints("RANCHO", "ballas")

-- Réinitialisation complète : toutes les factions dans tous les territoires
exports["drugs_creator"]:resetTerritoryPoints("*", "*")
```
