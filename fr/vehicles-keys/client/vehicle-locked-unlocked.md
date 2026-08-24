---
title: "Vehicle locked/unlocked"
description: "Se déclenche côté client quand l'état de verrouillage d'un véhicule change."
icon: "lock"
---

Se déclenche quand le verrou du véhicule a été basculé.

```lua Event
RegisterNetEvent("vehicles_keys:vehicleLockChanged", function(vehicle, isLocked)

end)
```

### Paramètres

| Nom       | Type de donnée | Description                            |
| ---------- | --------- | ------------------------------------------ |
| `vehicle`  | integer   | Handle du véhicule                                |
| `isLocked` | boolean   | Si le véhicule est maintenant verrouillé ou non        |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:vehicleLockChanged", function(vehicle, isLocked)
    print("The vehicle " .. vehicle .. " is now " .. (isLocked and "locked" or "unlocked"))
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
