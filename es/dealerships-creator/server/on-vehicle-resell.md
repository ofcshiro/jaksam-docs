---
title: "Al revender un vehículo"
description: "Se activa en el servidor después de que un jugador revende un vehículo a un concesionario."
icon: "hand-holding-dollar"
---

Este event se activa después de que un jugador revende un vehículo a un concesionario.

```lua Event
AddEventHandler("dealerships_creator:dealerships:onVehicleResell", function(dealershipId, plate, vehicleName, playerId, resellPrice)

end)
```

### Parámetros

| Nombre           | Tipo de dato | Descripción                                     |
| -------------- | --------- | ---------------------------------------------------- |
| `dealershipId` | integer   | El ID del concesionario donde se revendió el vehículo          |
| `plate`        | string    | La placa del vehículo                                     |
| `vehicleName`  | string    | El nombre de spawn del vehículo                                  |
| `playerId`     | integer   | Server ID del jugador que revendió el vehículo                  |
| `resellPrice`  | integer   | Cantidad de dinero que recibió el jugador                       |
