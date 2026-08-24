---
title: "Integrate external impound script"
description: "Connecte ton propre script de fourrière à Jobs Creator quand un véhicule est mis en fourrière."
icon: "warehouse"
---

Se déclenche quand un véhicule est mis en fourrière.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:actions:vehicleImpounded", function(vehiclePlate, vehicleModel)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:actions:vehicleImpounded", function(vehiclePlate, vehicleModel)
    -- You can add your impound script exports here
    TriggerServerEvent("impound_script:impoundVehicle", vehiclePlate, vehicleModel)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehiclePlate` | string | La plaque du véhicule |
| `vehicleModel` | string | Le modèle du véhicule |
