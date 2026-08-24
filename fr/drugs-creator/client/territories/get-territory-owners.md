---
title: "Get territory owners"
description: "Récupère le propriétaire actuel de chaque territoire."
icon: "flag"
---

Retourne une table contenant le propriétaire actuel de chaque territoire.

```lua Export
local owners = exports["drugs_creator"]:getTerritoryOwners()
```

### Retour

| Type de donnée | Description                                                                    |
| --------- | ----------------------------------------------------------------------------------- |
| table     | Une table où clé = nom du territoire et valeur = nom du job/de la gang propriétaire, ou `nil`         |

## Exemple

```lua
local owners = exports["drugs_creator"]:getTerritoryOwners()

for territoryName, ownerFaction in pairs(owners) do
    print(territoryName .. " is owned by " .. (ownerFaction or "nobody"))
end
```
