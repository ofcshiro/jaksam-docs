---
title: "Replace default police alert"
description: "Reemplaza el comportamiento de alerta a la policía del lado cliente por el tuyo propio."
icon: "siren-on"
---

<Warning>
  Se activa cuando se alerta a la policía. Esto se activa en **cada** cliente de jugador policía — si buscas un único evento, revisa la categoría del lado servidor.
</Warning>

```lua Event
RegisterNetEvent("vehicles_keys:alertedPolice", function(coords, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordenadas donde se activó la alerta     |
| `message` | string    | El mensaje que verá el policía                  |

## Ejemplo

```lua
-- Desactiva la alerta a la policía predeterminada
RegisterNetEvent("vehicles_keys:framework:ready", function()
    exports["vehicles_keys"]:disableScriptEvent("vehicles_keys:alertedPolice")
end)

RegisterNetEvent("vehicles_keys:alertedPolice", function(coords, message)
    -- Haz algo
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
