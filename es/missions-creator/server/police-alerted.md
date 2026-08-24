---
title: "Police alerted"
description: "Se dispara del lado del servidor, una vez por alerta, cuando se alerta a la policía."
icon: "siren-on"
---

<Warning>
  Se dispara cuando se alerta a la policía del lado del servidor (solo **1** vez por alerta, en lugar de en cada jugador como en el evento del lado del cliente).
</Warning>

```lua Event
RegisterNetEvent("missions_creator:alertedPolice", function(coords, message)

end)
```

### Parámetros

| Nombre      | Tipo de dato | Descripción                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordenadas donde se disparó la alerta     |
| `message` | string    | Mensaje que se mostraría               |

## Ejemplo

```lua
RegisterNetEvent("missions_creator:alertedPolice", function(coords, message)
    -- solo un ejemplo, NO funcionará
    TriggerClientEvent("news_script:heistAlert", -1, coords, message)
end)
```

<Note>
  Coloca este código en el archivo `jaksam_core/config/sv_config.lua`, al final del archivo en líneas nuevas.
</Note>
