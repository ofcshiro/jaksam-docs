---
title: "Set identifier queue priority"
description: "Establece una prioridad de queue para un identifier."
icon: "arrow-up-short-wide"
---

Establece la prioridad de queue de un identifier.

<CodeGroup>

```lua Export
exports["easy_allowlist"]:setIdentifierQueuePriority(identifier, priority)
```

```lua Example
exports["easy_allowlist"]:setIdentifierQueuePriority("steam:71002010c2f9c5d", 15)
```

</CodeGroup>

### Parámetros

| Nombre         | Tipo de dato | Descripción                |
| ------------ | --------- | ---------------------------- |
| `identifier` | string    | El identifier principal del jugador |
| `priority`   | integer   | Prioridad de la queue               |
