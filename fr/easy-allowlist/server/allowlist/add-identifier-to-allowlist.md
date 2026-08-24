---
title: "Add identifier to allowlist"
description: "Ajoute un identifier à l'allowlist."
icon: "user-plus"
---

Ajoute l'allowlist pour un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:addIdentifierToAllowlist(identifier)
```

```lua Example
exports["easy_allowlist"]:addIdentifierToAllowlist("steam:71002010c2f9c5d")
```

</CodeGroup>

### Paramètres

| Nom         | Type de donnée | Description                 |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | L'identifier principal du joueur |
