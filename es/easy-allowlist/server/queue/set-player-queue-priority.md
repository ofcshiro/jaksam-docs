---
title: "Set player queue priority"
description: "Establece una prioridad de queue para un ID de jugador online."
icon: "arrow-up-short-wide"
---

Establece una prioridad de queue para un ID de jugador online.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:setPlayerQueuePriority(playerId, priority)
```

```lua Example
local playerId = 61
exports["easy_allowlist"]:setPlayerQueuePriority(playerId, 15)
```

</CodeGroup>

### Parámetros

| Nombre       | Tipo de dato | Descripción       |
| ---------- | --------- | -------------------- |
| `playerId` | integer   | ID de servidor del jugador   |
| `priority` | integer   | Prioridad de la queue        |
