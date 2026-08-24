---
title: "Vehicle spawned"
description: "Se déclenche après le spawn d'un véhicule temporaire."
icon: "car"
---

Se déclenche après le spawn d'un véhicule temporaire.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:temporary_garage:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
end)
```

```lua Example
AddEventHandler("jobs_creator:temporary_garage:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
    -- Exemple pour donner les clés du véhicule (tu peux avoir un TriggerEvent à utiliser, c'est à toi de voir)
    giveKeysToVehicle(vehicle)
    print(vehicleName) -- Exemple de sortie 'adder'
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicle` | vehicle handle | Le handle du véhicule |
| `vehicleName` | string | Le nom du véhicule |
| `vehiclePlate` | string | La plaque du véhicule |
