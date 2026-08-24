---
title: "Sold by hired dealer"
description: "Déclenché côté serveur quand un hired dealer vend une drogue."
icon: "user-tie"
---

Déclenché côté serveur quand un hired dealer vend une drogue.

```lua Event
AddEventHandler("drugs_creator:hiredDealers:itemSold", function(ownerIdentifier, ownerJob, drugName, quantity, totalPrice, territoryName, accountName)

end)
```

### Paramètres

| Nom               | Type de donnée | Description                                              |
| -------------------- | --------- | ------------------------------------------------------------ |
| `ownerIdentifier`    | string    | Identifiant du personnage du propriétaire du dealer                       |
| `ownerJob`           | string    | Nom du job/de la gang du propriétaire au moment de l'embauche                   |
| `drugName`           | string    | ID de l'item de la drogue vendue                                             |
| `quantity`           | integer   | Quantité vendue                                                          |
| `totalPrice`         | integer   | Argent total gagné grâce à la vente                                        |
| `territoryName`      | string    | Nom du territoire où se trouve le dealer                         |
| `accountName`        | string    | Type de compte utilisé pour la récompense (money, black_money, etc.)                 |

## Exemple

```lua
AddEventHandler("drugs_creator:hiredDealers:itemSold", function(ownerIdentifier, ownerJob, drugName, quantity, totalPrice, territoryName, accountName)
    print(("[Hired Dealer] %s sold %dx %s for $%d in %s (owner: %s, account: %s)"):format(
        ownerJob, quantity, drugName, totalPrice, territoryName, ownerIdentifier, accountName
    ))
end)
```
