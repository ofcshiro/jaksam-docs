---
title: "Self remove vehicle plate"
description: "Elimina tus propias llaves de una placa de vehículo específica."
icon: "key"
---

Puedes usar este evento para eliminar tus propias llaves de una placa de vehículo, por ejemplo en los eventos en los que tu framework elimina un vehículo con el comando `/dv`.

```lua Event
TriggerServerEvent("vehicles_keys:selfRemoveKeys", plate)
```
