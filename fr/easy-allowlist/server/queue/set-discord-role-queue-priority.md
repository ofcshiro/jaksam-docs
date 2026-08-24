---
title: "Set Discord role queue priority"
description: "Définit une priorité de queue pour un rôle Discord."
icon: "arrow-up-short-wide"
---

Définit une priorité de queue pour un ID de rôle Discord.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:setDiscordRolePriority(discordRoleId, priority)
```

```lua Example
local discordRoleId = "332962646660794880"
exports["easy_allowlist"]:setDiscordRolePriority(discordRoleId, 30)
```

</CodeGroup>

### Paramètres

| Nom            | Type de donnée | Description       |
| ---------------- | --------- | ------------------- |
| `discordRoleId`  | string    | ID du rôle Discord     |
| `priority`       | integer   | Priorité de queue      |
