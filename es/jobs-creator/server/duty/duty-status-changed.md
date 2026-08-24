---
title: "Duty status changed"
description: "Se dispara después de que un jugador entra o sale de servicio, del lado del servidor."
icon: "briefcase"
---

Se dispara después de que un jugador entra/sale de servicio, del lado del servidor.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:toggleDuty", function(playerId, jobName, isOnDuty)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:toggleDuty", function(playerId, jobName, isOnDuty)
    if(isOnDuty) then
        TriggerEvent("external_scoreboard:increaseOnDutyCount", jobName)
    else
        TriggerEvent("external_scoreboard:decreaseOnDutyCount", jobName)
    end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador objetivo |
| `jobName` | string | ID del trabajo del jugador |
| `isOnDuty` | boolean | Nuevo estado de servicio del jugador |
