---
title: "Remove Discord role queue priority"
description: "Retire une priorité de queue pour un rôle Discord."
icon: "arrow-down-short-wide"
---

Retire une priorité de queue pour un rôle Discord.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:removeDiscordRoleQueuePriority(discordRoleId)
```

```lua Example
local discordRoleId = "332962646660794880"
exports["easy_allowlist"]:removeDiscordRoleQueuePriority(discordRoleId)
```

</CodeGroup>

### Paramètres

| Nom            | Type de donnée | Description      |
| ---------------- | --------- | ----------------- |
| `discordRoleId`  | string    | L'ID du rôle Discord |
