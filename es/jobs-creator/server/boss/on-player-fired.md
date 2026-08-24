---
title: "On player fired"
description: "Se dispara cuando un jugador ha sido despedido de un trabajo."
icon: "user-xmark"
---

Se dispara cuando un jugador ha sido despedido de un trabajo.

```lua Event
RegisterNetEvent("jobs_creator:boss:employeeFired", function(employeeIdentifier, jobName)
end)
```

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `employeeIdentifier` | string | Identificador del personaje del jugador |
| `jobName` | string | La ID del trabajo del que el jugador fue despedido |
