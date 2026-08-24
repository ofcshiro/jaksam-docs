---
title: "Get if a player is on duty"
description: "Comprueba si un jugador específico está actualmente en servicio."
icon: "briefcase"
---

Devuelve si el jugador está en servicio o no.

<CodeGroup>

```lua Export
exports["jobs_creator"]:isPlayerOnDuty(playerId)
```

```lua Example
local playerId = 52
print("Player ID " .. playerId .. " is on duty: " .. tostring(exports["jobs_creator"]:isPlayerOnDuty(playerId)))
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador objetivo |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isOnDuty` | boolean | **true** si el jugador está en servicio, **false** si el jugador está fuera de servicio |
