---
title: "Toggle closest vehicle lock"
description: "Bascule manuellement le verrou du véhicule le plus proche."
icon: "lock"
---

Cet export peut être utilisé pour basculer manuellement le verrou d'un véhicule.

```lua Export
exports["vehicles_keys"]:toggleClosestVehicleLock()
```

## Exemple

```lua
RegisterCommand("togglelock", function(_, args)
    exports["vehicles_keys"]:toggleClosestVehicleLock()
end)
```
