---
title: "Abrir el menú manualmente"
description: "Activa la apertura del menú de Blips Creator desde tu propio código del lado del cliente."
icon: "map-location-dot"
---

Puedes usar este event desde cualquier lugar **del lado del cliente** para abrir el menú.

```lua Event
TriggerEvent("blips_creator:openBlipsMenu")
```

## Ejemplo

Puedes abrir el menú con un comando, por ejemplo:

```lua
RegisterCommand("blipscreator", function()
    TriggerEvent("blips_creator:openBlipsMenu")
end)
```
