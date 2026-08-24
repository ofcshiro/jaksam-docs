---
title: "Replace default police alert"
description: "Reemplaza el comportamiento de la alerta policial del lado del cliente con el tuyo propio."
icon: "siren-on"
---

<Warning>
  Se dispara cuando se alerta a la policía. Esto se dispara en el cliente de **cada** jugador policía — si buscas un event único, consulta la categoría del lado del servidor.
</Warning>

```lua Event
RegisterNetEvent("races_creator:alertedPolice", function(coords, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordenadas donde se disparó la alerta     |
| `message` | string    | El mensaje que verá el policía                  |

## Ejemplo

```lua
-- Deshabilita la alerta policial predeterminada
RegisterNetEvent("races_creator:framework:ready", function()
    exports["races_creator"]:disableScriptEvent("races_creator:alertedPolice")
end)

RegisterNetEvent("races_creator:alertedPolice", function(coords, message)
    -- Haz algo
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
