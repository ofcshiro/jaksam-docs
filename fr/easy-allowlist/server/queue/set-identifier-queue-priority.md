---
title: "Set identifier queue priority"
description: "Définit une priorité de queue pour un identifier."
icon: "arrow-up-short-wide"
---

Définit la priorité de queue d'un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:setIdentifierQueuePriority(identifier, priority)
```

```lua Example
exports["easy_allowlist"]:setIdentifierQueuePriority("steam:71002010c2f9c5d", 15)
```

</CodeGroup>

### Paramètres

| Nom         | Type de donnée | Description                |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | L'identifier principal du joueur |
| `priority`   | integer   | Priorité de queue               |
