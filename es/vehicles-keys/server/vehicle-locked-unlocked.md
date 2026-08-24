---
title: "Vehicle locked/unlocked"
description: "Se activa del lado servidor cuando cambia el estado de bloqueo de un vehículo."
icon: "lock"
---

Se activa cuando se ha alternado el bloqueo del vehículo.

```lua Event
RegisterNetEvent("vehicles_keys:vehicleLockChanged", function(vehicle, isLocked)

end)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                            |
| ---------- | --------- | ------------------------------------------ |
| `vehicle`  | integer   | Handle del vehículo                                |
| `isLocked` | boolean   | Si el vehículo está ahora bloqueado o no        |

## Ejemplo

```lua
RegisterNetEvent("vehicles_keys:vehicleLockChanged", function(vehicle, isLocked)
    print("The vehicle " .. vehicle .. " is now " .. (isLocked and "locked" or "unlocked"))
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
