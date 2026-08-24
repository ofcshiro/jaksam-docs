---
title: "Toggle hotwiring"
description: "Activa o desactiva el puenteo temporalmente para el jugador."
icon: "bolt"
---

Este export es útil cuando quieres que el jugador **temporalmente** ya no pueda usar el puenteo.

```lua Export
exports["vehicles_keys"]:toggleHotwiring(newState)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                            |
| ---------- | --------- | ---------------------------------------------------------- |
| `newState` | boolean   | `true` = puenteo activado, `false` = puenteo desactivado       |

## Ejemplo

```lua
RegisterNetEvent("vehicle_shop:enteredList", function()
    exports["vehicles_keys"]:toggleHotwiring(false)
end)

RegisterNetEvent("vehicle_shop:exitedList", function()
    exports["vehicles_keys"]:toggleHotwiring(true)
end)
```
