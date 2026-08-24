---
title: "Self give vehicle plate"
description: "Date a ti mismo las llaves de una placa de vehículo específica."
icon: "key"
---

Puedes usar este evento para darte a ti mismo una placa de vehículo, por ejemplo en los eventos en los que tu framework genera un vehículo con el comando `/car`.

```lua Event
TriggerServerEvent("vehicles_keys:selfGiveVehicleKeys", plate)
```

### Nota

Si quieres una forma más sencilla de darte a ti mismo las llaves del vehículo que estás conduciendo actualmente, consulta [esta página](/es/vehicles-keys/client/self-give-current-vehicle-plate).
