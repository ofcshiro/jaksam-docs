---
title: "Sold by hired dealer"
description: "Se activa del lado del servidor cuando un hired dealer vende una droga."
icon: "user-tie"
---

Se activa en el servidor cuando un hired dealer vende una droga.

```lua Event
AddEventHandler("drugs_creator:hiredDealers:itemSold", function(ownerIdentifier, ownerJob, drugName, quantity, totalPrice, territoryName, accountName)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                              |
| -------------------- | --------- | ------------------------------------------------------------ |
| `ownerIdentifier`    | string    | Identificador del personaje del propietario del dealer                       |
| `ownerJob`           | string    | Nombre del job/gang del propietario en el momento de la contratación                   |
| `drugName`           | string    | ID del item de la droga vendida                                             |
| `quantity`           | integer   | Cantidad vendida                                                          |
| `totalPrice`         | integer   | Dinero total obtenido con la venta                                        |
| `territoryName`      | string    | Nombre del territorio donde se encuentra el dealer                         |
| `accountName`        | string    | Tipo de cuenta usada para la recompensa (money, black_money, etc.)                 |

## Ejemplo

```lua
AddEventHandler("drugs_creator:hiredDealers:itemSold", function(ownerIdentifier, ownerJob, drugName, quantity, totalPrice, territoryName, accountName)
    print(("[Hired Dealer] %s sold %dx %s for $%d in %s (owner: %s, account: %s)"):format(
        ownerJob, quantity, drugName, totalPrice, territoryName, ownerIdentifier, accountName
    ))
end)
```
