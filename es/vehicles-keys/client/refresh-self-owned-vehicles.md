---
title: "Refresh self owned vehicles"
description: "Actualiza la lista de vehículos propios del jugador local del lado cliente, por ejemplo después de comprar un vehículo nuevo."
icon: "rotate"
---

Activar este evento (desde el lado cliente) actualizará la lista de vehículos propios del jugador (desde `owned_vehicles` en ESX o `player_vehicles` en QBCore).

Esto es útil para actualizar la lista de vehículos propios cuando un jugador compra un vehículo nuevo — puedes añadir esta línea de código justo después de una compra de vehículo exitosa.

```lua Event
TriggerServerEvent("vehicles_keys:refreshMineOwnedVehicles")
```
