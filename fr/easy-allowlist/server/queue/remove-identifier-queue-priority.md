---
title: "Remove identifier queue priority"
description: "Retire une priorité de queue pour un identifier."
icon: "arrow-down-short-wide"
---

Retire une priorité de queue pour un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:removeIdentifierQueuePriority(identifier)
```

```lua Example
exports["easy_allowlist"]:removeIdentifierQueuePriority("steam:71002010c2f9c5d")
```

</CodeGroup>

### Paramètres

| Nom         | Type de donnée | Description                 |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | L'identifier principal du joueur |
