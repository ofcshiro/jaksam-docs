---
title: "Robo iniciado"
description: "Se activa cuando empieza un robo."
icon: "play"
---

Se activa cuando se termina un paso en la primera etapa de un robo que aún no ha comenzado.

```lua Event
RegisterNetEvent("robberies_creator:heist:heistStarted", function(heistId)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción        |
| --------- | --------- | --------------------- |
| `heistId` | integer   | ID del robo        |

## Ejemplo

```lua
RegisterNetEvent("robberies_creator:heist:heistStarted", function(heistId)
    -- solo un ejemplo, no hará nada útil, puede que quieras obtener datos de la base de datos

    print("Heist with ID " .. heistId .. " has just started")
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
