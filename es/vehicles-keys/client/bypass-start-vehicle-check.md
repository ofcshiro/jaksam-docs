---
title: "Bypass start vehicle check"
description: "Omite las condiciones de arranque del vehículo usando un state bag."
icon: "key"
---

Puedes omitir la comprobación de arranque del vehículo estableciendo el state bag `canAlwaysStart` en `true`.

## Ejemplo

```lua
-- Este comando hará que el jugador omita las condiciones de arranque del vehículo actual
RegisterCommand("startbypass", function()
    local plyPed = PlayerPedId()
    local plyVeh = GetVehiclePedIsIn(plyPed)

    Entity(plyVeh).state.canAlwaysStart = true
end)
```

<Note>
  El bypass se aplica cuando entras al vehículo **después** de que haya sido activado.
</Note>
