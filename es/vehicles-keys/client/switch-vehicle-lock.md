---
title: "Switch vehicle lock"
description: "Cambia el bloqueo de un vehículo, revocando las llaves compartidas previamente por el dueño."
icon: "key"
---

Activar este evento (desde el lado cliente) cambiará el bloqueo del vehículo con esa placa, eliminando todas las llaves compartidas previamente por el dueño a otros jugadores.

```lua Event
TriggerServerEvent("vehicles_keys:switchLock", plate)
```

### Parámetros

| Nombre    | Tipo de dato | Descripción                |
| ------- | --------- | ------------------------------ |
| `plate` | string    | La placa del vehículo          |
