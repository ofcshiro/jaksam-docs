---
title: "Au spawn du véhicule d'essai"
description: "Se déclenche côté client après qu'un véhicule d'essai a été généré."
icon: "car-side"
---

Cet event se déclenche après qu'un véhicule d'essai a été généré sur le client effectuant l'essai.

```lua Event
AddEventHandler("dealerships_creator:testDrive:vehicleSpawned", function(vehicle, vehicleNetId, plate)

end)
```

### Paramètres

| Nom           | Type de donnée | Description               |
| -------------- | --------- | ---------------------------- |
| `vehicle`      | integer   | Le handle du véhicule             |
| `vehicleNetId` | integer   | L'ID réseau du véhicule          |
| `plate`        | string    | La plaque du véhicule             |

## Exemple

```lua
AddEventHandler("dealerships_creator:testDrive:vehicleSpawned", function(vehicle, vehicleNetId, plate)
    SetVehicleFuelLevel(vehicle, 100.0)

    -- Tu voudras peut-être donner les clés du véhicule d'une façon ou d'une autre
end)
```
