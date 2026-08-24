---
title: "Set player queue priority"
description: "Définit une priorité de queue pour un ID de joueur en ligne."
icon: "arrow-up-short-wide"
---

Définit une priorité de queue pour un ID de joueur en ligne.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:setPlayerQueuePriority(playerId, priority)
```

```lua Example
local playerId = 61
exports["easy_allowlist"]:setPlayerQueuePriority(playerId, 15)
```

</CodeGroup>

### Paramètres

| Nom       | Type de donnée | Description       |
| ---------- | --------- | -------------------- |
| `playerId` | integer   | Server ID du joueur   |
| `priority` | integer   | Priorité de queue        |
