---
title: "Vehicle spawned"
description: "Se déclenche après le spawn d'un véhicule depuis le garage de véhicules possédés."
icon: "car"
---

Se déclenche après le spawn d'un véhicule depuis le garage de véhicules possédés.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:garage_owned:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
end)
```

```lua Example
AddEventHandler("jobs_creator:garage_owned:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
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
