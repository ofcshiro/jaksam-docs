---
title: "Iniciar el botón de pánico manualmente"
description: "Activa el botón de pánico desde tu propio código, sin necesidad de la tecla rápida."
icon: "hand-pointer"
---

Puedes usar este event para iniciar manualmente el botón de pánico, sin que el jugador tenga que pulsar la tecla rápida en absoluto — por ejemplo, desde un menú radial.

<Note>
  La tecla rápida del botón de pánico se puede desactivar en la configuración del menú.
</Note>

```lua Event
TriggerServerEvent("trackers_creator:panicButtonPressed")
```
