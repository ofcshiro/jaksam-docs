---
title: "UI activada/desactivada"
description: "Oculta o muestra tu propia interfaz cuando se activa o desactiva la UI de la tienda."
icon: "eye"
---

Útil para ocultar/mostrar tu interfaz cuando se activa o desactiva la UI de la tienda.

## UI de la tienda activada

```lua
RegisterNetEvent("shops_creator:ui:show", function()
    -- Desactiva tu interfaz aquí con tu propio código
end)
```

## UI de la tienda desactivada

```lua
RegisterNetEvent("shops_creator:ui:hide", function()
    -- Activa tu interfaz aquí con tu propio código
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
