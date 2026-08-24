---
title: "Toggle current duty status"
description: "Disparador para alternar o establecer explícitamente el estado de servicio actual del jugador."
icon: "briefcase"
---

Disparador para alternar el estado de servicio actual del jugador.

## Alternar

Esto alternará el estado de servicio actual del jugador (si estaba fuera de servicio, entrará en servicio, y viceversa).

<CodeGroup>

```lua Event
TriggerEvent("jobs_creator:toggleCurrentDutyStatus")
```

```lua Example
-- Alterna el estado de servicio actual
RegisterCommand("duty", function()
    TriggerEvent("jobs_creator:toggleCurrentDutyStatus")
end, false)
```

</CodeGroup>

## Establecer explícitamente

Esto establecerá el estado de servicio del jugador al estado indicado en lugar de alternarlo.

<CodeGroup>

```lua Event
TriggerEvent("jobs_creator:toggleCurrentDutyStatus", newDutyStatus)
```

```lua Example
RegisterCommand("onduty", function()
    TriggerEvent("jobs_creator:toggleCurrentDutyStatus", true)
end, false)
RegisterCommand("offduty", function()
    TriggerEvent("jobs_creator:toggleCurrentDutyStatus", false)
end, false)
```

</CodeGroup>
