---
title: "Self give current vehicle plate"
description: "Donne-toi les clés du véhicule que tu conduis actuellement, sans avoir besoin de sa plaque."
icon: "car-side"
---

Cet event fait la même chose que [Self give vehicle plate](/fr/vehicles-keys/client/self-give-vehicle-plate), mais c'est encore plus simple puisqu'il ne nécessite aucun paramètre — c'est juste une ligne à copier-coller.

Déclencher cet event trouvera automatiquement le véhicule que conduit le joueur local et lui donnera ses clés.

```lua Event
TriggerServerEvent("vehicles_keys:selfGiveCurrentVehicleKeys")
```

## Exemple

```lua
-- Juste un event d'un script imaginaire d'auto-école
RegisterNetEvent("driving_school:test_started", function()
    local vehicle = CreateVehicle("blista", 249.40, -1407.23, 30.40, true, false)
    SetVehicleColours(vehicle, 4, 5)
    SetVehicleExtraColours(vehicle, 1, 2)
    SetEntityHeading(vehicle, 317.64)
    SetVehicleOnGroundProperly(vehicle)
    SetPedIntoVehicle(PlayerPedId(), vehicle, -1)

    -- INTÉGRATION VEHICLES KEYS POUR DONNER LES CLÉS FACILEMENT
    TriggerServerEvent("vehicles_keys:selfGiveCurrentVehicleKeys")
end)
```
