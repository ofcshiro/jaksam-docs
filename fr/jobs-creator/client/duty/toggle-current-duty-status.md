---
title: "Toggle current duty status"
description: "Déclencheur pour basculer ou définir explicitement le statut de service actuel du joueur."
icon: "briefcase"
---

Déclencheur pour basculer le statut de service actuel du joueur.

## Basculer

Ceci bascule le statut de service actuel du joueur (s'il était hors service, il prend son service, et vice versa).

<CodeGroup>

```lua Event
TriggerEvent("jobs_creator:toggleCurrentDutyStatus")
```

```lua Example
-- Bascule le statut de service actuel
RegisterCommand("duty", function()
    TriggerEvent("jobs_creator:toggleCurrentDutyStatus")
end, false)
```

</CodeGroup>

## Définir explicitement

Ceci définit le statut de service du joueur au statut donné au lieu de le basculer.

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
