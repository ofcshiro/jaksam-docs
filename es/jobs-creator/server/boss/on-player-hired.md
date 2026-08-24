---
title: "On player hired"
description: "Se dispara cuando un jugador ha sido contratado para un trabajo."
icon: "user-plus"
---

Se dispara cuando un jugador ha sido contratado para un trabajo.

```lua Event
RegisterNetEvent("jobs_creator:boss:playerHired", function(playerId, jobName)
end)
```

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `jobName` | string | La ID del trabajo para el que el jugador fue contratado |
