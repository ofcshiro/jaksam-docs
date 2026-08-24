---
title: "Get if a player is on duty"
description: "Vérifie si un joueur spécifique est actuellement en service."
icon: "briefcase"
---

Retourne si le joueur est en service ou non.

<CodeGroup>

```lua Export
exports["jobs_creator"]:isPlayerOnDuty(playerId)
```

```lua Example
local playerId = 52
print("Player ID " .. playerId .. " is on duty: " .. tostring(exports["jobs_creator"]:isPlayerOnDuty(playerId)))
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Server ID du joueur cible |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isOnDuty` | boolean | **true** si le joueur est en service, **false** s'il est hors service |
