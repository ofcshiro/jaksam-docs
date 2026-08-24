---
title: "Add society account money"
description: "Ajoute de l'argent au compte société d'un job."
icon: "sack-dollar"
---

Ajoute de l'argent à une société.

<CodeGroup>

```lua Export
exports["jobs_creator"]:addSocietyMoney(jobName, amount)
```

```lua Example
local isSuccessful = exports["jobs_creator"]:addSocietyMoney("police", 5000)
print(isSuccessful)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `jobName` | string | ID du job (exemple : police) |
| `amount` | integer | Montant d'argent à ajouter |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isSuccessful` | boolean | Indique si l'argent a été ajouté ou non |
