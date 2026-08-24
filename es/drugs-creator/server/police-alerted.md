---
title: "Police alerted"
description: "Se activa del lado del servidor, una vez por alerta, cuando se alerta a la policía."
icon: "siren-on"
---

Se activa cuando se alerta a la policía del lado del servidor (solo **1** vez por alerta, en lugar de para cada jugador como ocurre del lado del cliente).

```lua Event
RegisterNetEvent("drugs_creator:alertedPolice", function(coords, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordenadas donde se activó la alerta     |
| `message` | string    | Mensaje que se mostraría               |

## Ejemplo

```lua
RegisterNetEvent("drugs_creator:alertedPolice", function(coords, message)
    -- solo un ejemplo, NO funcionará
    TriggerClientEvent("news_script:heistAlert", -1, coords, message)
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
