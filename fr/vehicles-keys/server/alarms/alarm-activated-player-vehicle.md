---
title: "Alarm activated (player vehicle)"
description: "Se déclenche côté serveur quand une alarme est activée sur un véhicule de joueur."
icon: "car"
---

Se déclenche quand une alarme d'un véhicule de joueur est activée.

```lua Event
RegisterNetEvent("vehicles_keys:alarmOnPlayerVehicle", function(vehicle, vehicleCoords, alarmLevel)

end)
```

### Paramètres

| Nom            | Type de donnée | Description                       |
| --------------- | --------- | -------------------------------------- |
| `vehicle`       | integer   | Handle du véhicule                            |
| `vehicleCoords` | vector3   | Les coordonnées du véhicule              |
| `alarmLevel`    | integer   | Le niveau de l'alarme installée             |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:alarmOnPlayerVehicle", function(vehicle, vehicleCoords, alarmLevel)
    -- Tu peux ajouter une notification externe si tu le souhaites
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
