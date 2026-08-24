---
title: "Remove identifier from allowlist"
description: "Retire un identifier de l'allowlist."
icon: "user-minus"
---

Retire l'allowlist pour un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:removeAllowlistFromIdentifier(identifier)
```

```lua Example
exports["easy_allowlist"]:removeAllowlistFromIdentifier("steam:71002010c2f9c5d")
```

</CodeGroup>

### Paramètres

| Nom         | Type de donnée | Description                 |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | L'identifier principal du joueur |
