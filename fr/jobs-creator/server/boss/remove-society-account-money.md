---
title: "Remove society account money"
description: "Retire de l'argent du compte société d'un job."
icon: "sack-dollar"
---

Retire de l'argent d'une société.

<CodeGroup>

```lua Export
exports["jobs_creator"]:removeSocietyMoney(jobName, amount)
```

```lua Example
local isSuccessful = exports["jobs_creator"]:removeSocietyMoney("police", 5000)
print(isSuccessful)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `jobName` | string | ID du job (exemple : police) |
| `amount` | integer | Montant d'argent à retirer |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isSuccessful` | boolean | Indique si l'argent a été retiré ou non |
