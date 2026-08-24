---
title: "Duty status changed"
description: "Se déclenche après qu'un joueur prend ou quitte son service, côté serveur."
icon: "briefcase"
---

Se déclenche après qu'un joueur prend/quitte son service, côté serveur.

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

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Server ID du joueur cible |
| `jobName` | string | ID du job du joueur |
| `isOnDuty` | boolean | Le nouveau statut de service du joueur |
