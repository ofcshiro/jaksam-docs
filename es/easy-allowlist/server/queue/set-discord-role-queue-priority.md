---
title: "Set Discord role queue priority"
description: "Establece una prioridad de queue para un rol de Discord."
icon: "arrow-up-short-wide"
---

Establece una prioridad de queue para un ID de rol de Discord.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:setDiscordRolePriority(discordRoleId, priority)
```

```lua Example
local discordRoleId = "332962646660794880"
exports["easy_allowlist"]:setDiscordRolePriority(discordRoleId, 30)
```

</CodeGroup>

### Parámetros

| Nombre            | Tipo de dato | Descripción       |
| ---------------- | --------- | ------------------- |
| `discordRoleId`  | string    | ID del rol de Discord     |
| `priority`       | integer   | Prioridad de la queue      |
