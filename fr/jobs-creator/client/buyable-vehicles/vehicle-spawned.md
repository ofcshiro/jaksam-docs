---
title: "Vehicle spawned"
description: "Se déclenche après le spawn d'un véhicule acheté depuis le garage de véhicules achetables."
icon: "car"
---

Se déclenche après le spawn d'un véhicule acheté depuis le garage de véhicules achetables.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:permanent_garage:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
end)
```

```lua Example
AddEventHandler("jobs_creator:permanent_garage:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
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
