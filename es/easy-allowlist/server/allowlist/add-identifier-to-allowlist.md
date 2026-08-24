---
title: "Add identifier to allowlist"
description: "Añade un identifier a la allowlist."
icon: "user-plus"
---

Da allowlist a un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:addIdentifierToAllowlist(identifier)
```

```lua Example
exports["easy_allowlist"]:addIdentifierToAllowlist("steam:71002010c2f9c5d")
```

</CodeGroup>

### Parámetros

| Nombre         | Tipo de dato | Descripción                 |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | El identifier principal del jugador |
