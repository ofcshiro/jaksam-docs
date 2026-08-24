---
title: "Get current territory"
description: "Obtén el nombre del territorio en el que se encuentra actualmente el jugador local."
icon: "map-pin"
---

Devuelve el nombre del territorio en el que se encuentra actualmente el jugador local, o `nil` si está fuera de cualquier territorio.

```lua Export
local territoryName = exports["drugs_creator"]:getCurrentTerritory()
```

### Valor de retorno

| Tipo de dato      | Descripción                                     |
| --------------- | -------------------------------------------------- |
| string / nil    | El nombre del territorio, o `nil` si el jugador no está en ninguno |

## Ejemplo

```lua
local territory = exports["drugs_creator"]:getCurrentTerritory()

if territory then
    print("You are in territory: " .. territory)
else
    print("You are not inside any territory")
end
```
