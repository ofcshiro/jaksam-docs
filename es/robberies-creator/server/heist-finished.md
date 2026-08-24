---
title: "Robo finalizado"
description: "Se activa cuando se completa un robo."
icon: "flag-checkered"
---

Se activa cuando se completa un robo (en el mismo momento en que la consola del servidor registra `"Heist has been completed"`).

```lua Event
RegisterNetEvent("robberies_creator:heist:heistFinished", function(heistId)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción        |
| --------- | --------- | --------------------- |
| `heistId` | integer   | ID del robo        |

## Ejemplo

```lua
RegisterNetEvent("robberies_creator:heist:heistFinished", function(heistId)
    -- solo un ejemplo, no hará nada útil, puede que quieras obtener datos de la base de datos

    print("Heist with ID " .. heistId .. " is finished")
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
