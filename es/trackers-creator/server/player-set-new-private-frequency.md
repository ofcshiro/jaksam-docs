---
title: "Jugador estableció nueva frecuencia privada"
description: "Se activa del lado del servidor cuando un jugador establece una nueva frecuencia privada de tracker."
icon: "sliders"
---

Este event se activa cuando un jugador usa el item de tracker privado y establece una nueva frecuencia.

```lua Event
AddEventHandler("trackers_creator:playerSetNewPrivateFrequency", function(playerId, trackerId)

end)
```

### Parámetros

| Nombre        | Tipo de dato | Descripción                 |
| ----------- | --------- | ------------------------------ |
| `playerId`  | integer   | El ID de servidor del jugador     |
| `frequency` | integer   | Nueva frecuencia elegida            |
