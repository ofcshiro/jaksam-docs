---
title: "Toggle hotwiring"
description: "Active ou désactive temporairement le court-circuitage pour le joueur."
icon: "bolt"
---

Cet export est utile quand tu veux que le joueur ne puisse plus **temporairement** utiliser le court-circuitage.

```lua Export
exports["vehicles_keys"]:toggleHotwiring(newState)
```

### Paramètres

| Nom       | Type de donnée | Description                                            |
| ---------- | --------- | ---------------------------------------------------------- |
| `newState` | boolean   | `true` = court-circuitage activé, `false` = court-circuitage désactivé       |

## Exemple

```lua
RegisterNetEvent("vehicle_shop:enteredList", function()
    exports["vehicles_keys"]:toggleHotwiring(false)
end)

RegisterNetEvent("vehicle_shop:exitedList", function()
    exports["vehicles_keys"]:toggleHotwiring(true)
end)
```
