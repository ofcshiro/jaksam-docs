---
title: "Get if local player owns a plate"
description: "Vérifie si le joueur local possède une plaque de véhicule spécifique."
icon: "circle-question"
---

Cet export permet de savoir si **le joueur local** possède une plaque de véhicule. Il vérifie aussi les plaques partagées, temporaires, etc.

```lua Export
exports["vehicles_keys"]:doesPlayerOwnPlate(plate)
```

### Paramètres

| Nom     | Type de donnée | Description                  |
| ------- | --------- | -------------------------------- |
| `plate` | string    | La plaque de véhicule à vérifier          |

### Valeur de retour

`true` si le véhicule est possédé.

`false` si le véhicule n'est pas possédé.

## Exemple

```lua
RegisterCommand("checkPlate", function(_, args)
    local plate = args[1] -- Exemple "ABC 123"

    if(exports["vehicles_keys"]:doesPlayerOwnPlate(plate)) then
        print("I own this vehicle plate")
    else
        print("I DO NOT own this vehicle plate")
    end
end)
```
