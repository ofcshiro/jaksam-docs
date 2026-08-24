---
title: "Get territory owners"
description: "Obtén el propietario actual de cada territorio."
icon: "flag"
---

Devuelve una tabla con el propietario actual de cada territorio.

```lua Export
local owners = exports["drugs_creator"]:getTerritoryOwners()
```

### Valor de retorno

| Tipo de dato | Descripción                                                                    |
| --------- | ----------------------------------------------------------------------------------- |
| table     | Una tabla donde key = nombre del territorio y value = nombre del job/gang propietario, o `nil`         |

## Ejemplo

```lua
local owners = exports["drugs_creator"]:getTerritoryOwners()

for territoryName, ownerFaction in pairs(owners) do
    print(territoryName .. " is owned by " .. (ownerFaction or "nobody"))
end
```
