---
title: "Toggle icon display"
description: "Muestra u oculta los iconos/texto de todas las puertas."
icon: "eye"
---

Alterna los iconos/texto de todas las puertas.

```lua Export
exports["doors_creator"]:toggleIconDisplay(newState)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                          |
| ---------- | --------- | ----------------------------------------------------- |
| `newState` | boolean   | `true` = mostrar icono/texto, `false` = ocultar icono/texto   |

## Ejemplo

```lua
RegisterCommand("hideDoorsIcon", function()
    exports["doors_creator"]:toggleIconDisplay(false)
end)
```
