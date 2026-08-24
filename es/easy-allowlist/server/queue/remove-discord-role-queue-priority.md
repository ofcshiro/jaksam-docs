---
title: "Remove Discord role queue priority"
description: "Elimina una prioridad de queue para un rol de Discord."
icon: "arrow-down-short-wide"
---

Elimina una prioridad de queue para un rol de Discord.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:removeDiscordRoleQueuePriority(discordRoleId)
```

```lua Example
local discordRoleId = "332962646660794880"
exports["easy_allowlist"]:removeDiscordRoleQueuePriority(discordRoleId)
```

</CodeGroup>

### Parámetros

| Nombre            | Tipo de dato | Descripción      |
| ---------------- | --------- | ----------------- |
| `discordRoleId`  | string    | El ID del rol de Discord |
