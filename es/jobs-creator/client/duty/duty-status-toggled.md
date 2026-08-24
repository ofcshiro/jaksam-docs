---
title: "Duty status toggled"
description: "Se dispara del lado del cliente después de que el jugador entra o sale de servicio."
icon: "briefcase"
---

Se dispara después de que el jugador entra/sale de servicio, del lado del cliente.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:toggleDuty", function(isOnDuty)
end)
```

```lua Example
AddEventHandler("jobs_creator:toggleDuty", function(isOnDuty)
    if(isOnDuty) then
        ESX.ShowNotification("You are now on duty")
    else
        ESX.ShowNotification("You are now off duty")
    end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isOnDuty` | boolean | El nuevo estado de servicio del jugador |
