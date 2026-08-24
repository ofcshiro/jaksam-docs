---
title: "Self give current vehicle plate"
description: "Date a ti mismo las llaves del vehículo que estás conduciendo actualmente, sin necesidad de su placa."
icon: "car-side"
---

Este evento hace lo mismo que [Self give vehicle plate](/es/vehicles-keys/client/self-give-vehicle-plate), pero es incluso más fácil ya que no requiere ningún parámetro — es solo una línea para copiar y pegar.

Activar este evento encontrará automáticamente el vehículo que está conduciendo el jugador local y le dará sus llaves.

```lua Event
TriggerServerEvent("vehicles_keys:selfGiveCurrentVehicleKeys")
```

## Ejemplo

```lua
-- Solo un evento de un script imaginario de autoescuela
RegisterNetEvent("driving_school:test_started", function()
    local vehicle = CreateVehicle("blista", 249.40, -1407.23, 30.40, true, false)
    SetVehicleColours(vehicle, 4, 5)
    SetVehicleExtraColours(vehicle, 1, 2)
    SetEntityHeading(vehicle, 317.64)
    SetVehicleOnGroundProperly(vehicle)
    SetPedIntoVehicle(PlayerPedId(), vehicle, -1)

    -- INTEGRACIÓN DE VEHICLES KEYS PARA DAR LAS LLAVES FÁCILMENTE
    TriggerServerEvent("vehicles_keys:selfGiveCurrentVehicleKeys")
end)
```
