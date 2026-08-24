---
title: "Get job account money"
description: "Obtén la cantidad de dinero almacenada en la cuenta de sociedad de un trabajo."
icon: "sack-dollar"
---

Obtén la cantidad de dinero almacenada en la cuenta de sociedad de un trabajo.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getJobAccountMoney(jobName)
```

```lua Example
local jobMoney = exports["jobs_creator"]:getJobAccountMoney("gang_job")
print(jobMoney)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `jobName` | string | ID del trabajo (ejemplo: police) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `accountMoney` | integer | Dinero almacenado en la cuenta de sociedad |
