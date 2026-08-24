---
title: "Get if player ID owns a plate"
description: "Vérifie si un joueur spécifique possède une plaque de véhicule côté serveur."
icon: "circle-question"
---

Cet export permet de savoir si un joueur possède une plaque de véhicule (vérifie aussi les plaques partagées, temporaires, etc.).

```lua Export
exports["vehicles_keys"]:isPlayerOwnerOfVehiclePlate(playerId, plate, onlyOwnedVehicles)
```

### Paramètres

| Nom                 | Type de donnée | Description                                                                                     |
| --------------------- | --------- | ---------------------------------------------------------------------------------------------------- |
| `playerId`             | integer   | L'ID serveur du joueur                                                                                   |
| `plate`                | string    | La plaque de véhicule à vérifier                                                                              |
| `onlyOwnedVehicles`    | boolean   | `true` = recherche uniquement dans les véhicules possédés. `false` = recherche aussi les véhicules temporaires, clés partagées, etc.         |

### Valeur de retour

`true` si le véhicule est possédé.

`false` si le véhicule n'est pas possédé.

## Exemple

```lua
RegisterCommand("checkPlate", function(playerId, args)
    local plate = args[1] -- Exemple "ABC 123"

    if(exports["vehicles_keys"]:isPlayerOwnerOfVehiclePlate(playerId, plate, false)) then
        print("I own this vehicle plate")
    else
        print("I DO NOT own this vehicle plate")
    end
end)
```
