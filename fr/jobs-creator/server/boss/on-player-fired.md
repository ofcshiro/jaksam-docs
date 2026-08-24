---
title: "On player fired"
description: "Déclenché lorsqu'un joueur a été licencié d'un job."
icon: "user-xmark"
---

Déclenché lorsqu'un joueur a été licencié d'un job.

```lua Event
RegisterNetEvent("jobs_creator:boss:employeeFired", function(employeeIdentifier, jobName)
end)
```

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `employeeIdentifier` | string | Identifiant du personnage du joueur |
| `jobName` | string | L'ID du job dont le joueur a été licencié |
