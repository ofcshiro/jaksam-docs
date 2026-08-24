---
title: "Vehicle parked"
description: "Se déclenche après qu'un véhicule du garage de véhicules possédés a été garé."
icon: "square-parking"
---

Se déclenche après que le véhicule du garage de véhicules possédés a été garé.

```lua Event
AddEventHandler("jobs_creator:garage_owned:vehicleParked", function(vehicleModel, vehiclePlate)
end)
```

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicleModel` | integer | Le modèle d'entité du véhicule |
| `vehiclePlate` | string | La plaque du véhicule |
