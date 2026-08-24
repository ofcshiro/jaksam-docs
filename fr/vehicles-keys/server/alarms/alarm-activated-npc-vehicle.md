---
title: "Alarm activated (NPC vehicle)"
description: "Se déclenche côté serveur quand une alarme est activée sur un véhicule PNJ."
icon: "car-side"
---

Se déclenche quand une alarme est déclenchée sur un véhicule PNJ.

```lua Event
RegisterNetEvent("vehicles_keys:alarmOnNPCVehicle", function(vehicle, vehicleCoords)

end)
```

### Paramètres

| Nom            | Type de donnée | Description                     |
| --------------- | --------- | ------------------------------------ |
| `vehicle`       | integer   | Handle du véhicule                          |
| `vehicleCoords` | vector3   | Les coordonnées du véhicule            |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:alarmOnNPCVehicle", function(vehicle, vehicleCoords)
    -- Tu peux ajouter une notification externe si tu le souhaites
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
