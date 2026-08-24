---
title: "Duty status toggled"
description: "Se déclenche côté client après que le joueur prend ou quitte son service."
icon: "briefcase"
---

Se déclenche après que le joueur prend/quitte son service, côté client.

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

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isOnDuty` | boolean | Le nouveau statut de service du joueur |
