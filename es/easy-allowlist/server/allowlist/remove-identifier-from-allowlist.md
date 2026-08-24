---
title: "Remove identifier from allowlist"
description: "Elimina un identifier de la allowlist."
icon: "user-minus"
---

Quita la allowlist a un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:removeAllowlistFromIdentifier(identifier)
```

```lua Example
exports["easy_allowlist"]:removeAllowlistFromIdentifier("steam:71002010c2f9c5d")
```

</CodeGroup>

### Parámetros

| Nombre         | Tipo de dato | Descripción                 |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | El identifier principal del jugador |
