---
title: "Ownership changed"
description: "Se déclenche côté serveur quand un territoire change de propriétaire."
icon: "flag"
---

Se déclenche sur le serveur quand un territoire change de propriétaire.

```lua Event
AddEventHandler("drugs_creator:territories:ownershipChanged", function(territoryName, newOwner, previousOwner)

end)
```

### Paramètres

| Nom              | Type de donnée    | Description                                           |
| ------------------ | ------------- | ----------------------------------------------------------- |
| `territoryName`     | string        | Le nom du territoire qui a changé de propriétaire                   |
| `newOwner`          | string / nil  | Le nom du job/gang du nouveau propriétaire, ou `nil` si perdu              |
| `previousOwner`     | string / nil  | Le nom du job/gang de l'ancien propriétaire, ou `nil`                  |

## Exemple

```lua
AddEventHandler("drugs_creator:territories:ownershipChanged", function(territoryName, newOwner, previousOwner)
    if newOwner then
        print(("%s is now owned by %s (was: %s)"):format(territoryName, newOwner, previousOwner or "nobody"))
    else
        print(("%s has been lost by %s"):format(territoryName, previousOwner or "unknown"))
    end
end)
```
