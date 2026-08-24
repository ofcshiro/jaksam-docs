---
title: "Toggle closest vehicle lock"
description: "Alterna manualmente el bloqueo del vehículo más cercano."
icon: "lock"
---

Este export se puede usar para alternar manualmente el bloqueo de un vehículo.

```lua Export
exports["vehicles_keys"]:toggleClosestVehicleLock()
```

## Ejemplo

```lua
RegisterCommand("togglelock", function(_, args)
    exports["vehicles_keys"]:toggleClosestVehicleLock()
end)
```
