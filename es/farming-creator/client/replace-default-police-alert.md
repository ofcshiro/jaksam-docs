---
title: "Reemplazar la alerta policial predeterminada"
description: "Reemplaza el comportamiento de la alerta policial del lado del cliente por el tuyo propio."
icon: "siren-on"
---

<Warning>
  Se activa cuando se alerta a la policía. Esto se activa en el cliente de **cada** jugador policía — si buscas un event único, consulta la categoría del lado del servidor.
</Warning>

```lua Event
RegisterNetEvent("farming_creator:alertedPolice", function(coords, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordenadas donde se activó la alerta     |
| `message` | string    | El mensaje que vería el policía                |

## Ejemplo

```lua
-- Desactiva la alerta policial predeterminada
RegisterNetEvent("farming_creator:framework:ready", function()
    exports["farming_creator"]:disableScriptEvent("farming_creator:alertedPolice")
end)

RegisterNetEvent("farming_creator:alertedPolice", function(coords, message)
    -- Do something
end)
```

<Note>
  Coloca este código en el archivo `integrations/cl_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
