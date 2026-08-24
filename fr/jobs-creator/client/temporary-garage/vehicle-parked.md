---
title: "Vehicle parked"
description: "Se déclenche après qu'un véhicule du garage temporaire a été garé."
icon: "square-parking"
---

Se déclenche après que le véhicule du garage temporaire a été garé.

```lua Event
AddEventHandler("jobs_creator:temporary_garage:vehicleParked", function(vehicleModel, vehiclePlate)
end)
```

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicleModel` | integer | Le modèle d'entité du véhicule |
| `vehiclePlate` | string | La plaque du véhicule |
