---
title: "Add society account money"
description: "Añade dinero a la cuenta de sociedad de un trabajo."
icon: "sack-dollar"
---

Añade dinero a una sociedad.

<CodeGroup>

```lua Export
exports["jobs_creator"]:addSocietyMoney(jobName, amount)
```

```lua Example
local isSuccessful = exports["jobs_creator"]:addSocietyMoney("police", 5000)
print(isSuccessful)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `jobName` | string | ID del trabajo (ejemplo: police) |
| `amount` | integer | Cantidad de dinero a añadir |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isSuccessful` | boolean | Si el dinero fue añadido o no |
