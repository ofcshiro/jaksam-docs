---
title: "On player hired"
description: "Déclenché lorsqu'un joueur a été embauché pour un job."
icon: "user-plus"
---

Déclenché lorsqu'un joueur a été embauché pour un job.

```lua Event
RegisterNetEvent("jobs_creator:boss:playerHired", function(playerId, jobName)
end)
```

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | ID serveur du joueur |
| `jobName` | string | L'ID du job pour lequel le joueur a été embauché |
