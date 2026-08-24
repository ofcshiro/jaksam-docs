---
title: "Get job account money"
description: "Récupère le montant d'argent stocké dans le compte société d'un job."
icon: "sack-dollar"
---

Récupère le montant d'argent stocké dans le compte société d'un job.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getJobAccountMoney(jobName)
```

```lua Example
local jobMoney = exports["jobs_creator"]:getJobAccountMoney("gang_job")
print(jobMoney)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `jobName` | string | ID du job (exemple : police) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `accountMoney` | integer | Argent stocké dans le compte société |
