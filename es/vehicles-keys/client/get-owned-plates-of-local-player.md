---
title: "Get owned plates of local player"
description: "Obtén todas las placas de vehículo propiedad del jugador local."
icon: "list"
---

Este export obtiene todas las placas propias de **el jugador local**.

```lua Export
local ownedPlates = exports["vehicles_keys"]:getOwnedVehiclePlates()
```

### Valor de retorno

Una tabla que contiene todas las placas propias, con el siguiente formato:

```lua
{
    ["ABC123"] = {
        type = "owned",
        model = -35726841
    },

    ["BCD473"] = {
        type = "temporary",
        model = -55726841
    },
}
```
