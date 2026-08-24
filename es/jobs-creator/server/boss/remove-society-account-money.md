---
title: "Remove society account money"
description: "Elimina dinero de la cuenta de sociedad de un trabajo."
icon: "sack-dollar"
---

Elimina dinero de una sociedad.

<CodeGroup>

```lua Export
exports["jobs_creator"]:removeSocietyMoney(jobName, amount)
```

```lua Example
local isSuccessful = exports["jobs_creator"]:removeSocietyMoney("police", 5000)
print(isSuccessful)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `jobName` | string | ID del trabajo (ejemplo: police) |
| `amount` | integer | Cantidad de dinero a eliminar |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isSuccessful` | boolean | Si el dinero fue eliminado o no |
