---
title: "Ownership changed"
description: "Se activa del lado del servidor cuando un territorio cambia de propietario."
icon: "flag"
---

Se activa en el servidor cuando un territorio cambia de propietario.

```lua Event
AddEventHandler("drugs_creator:territories:ownershipChanged", function(territoryName, newOwner, previousOwner)

end)
```

### Parámetros

| Nombre              | Tipo de dato    | Descripción                                           |
| ------------------ | ------------- | ----------------------------------------------------------- |
| `territoryName`     | string        | El nombre del territorio que cambió de propietario                   |
| `newOwner`          | string / nil  | El nombre del job/gang del nuevo propietario, o `nil` si se perdió              |
| `previousOwner`     | string / nil  | El nombre del job/gang del propietario anterior, o `nil`                  |

## Ejemplo

```lua
AddEventHandler("drugs_creator:territories:ownershipChanged", function(territoryName, newOwner, previousOwner)
    if newOwner then
        print(("%s is now owned by %s (was: %s)"):format(territoryName, newOwner, previousOwner or "nobody"))
    else
        print(("%s has been lost by %s"):format(territoryName, previousOwner or "unknown"))
    end
end)
```
