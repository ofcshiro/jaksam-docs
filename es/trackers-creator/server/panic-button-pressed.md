---
title: "Botón de pánico presionado"
description: "Se activa del lado del servidor cuando un jugador usa el botón de pánico."
icon: "triangle-exclamation"
---

Este event se activa cuando un jugador usa el botón de pánico.

```lua Event
AddEventHandler("trackers_creator:playerPressedPanicButton", function(playerId)

end)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                              |
| ---------- | --------- | ---------------------------------------------------------- |
| `playerId` | integer   | El ID de servidor del jugador que presionó el botón de pánico   |

## Ejemplo

```lua
RegisterNetEvent("trackers_creator:playerPressedPanicButton", function(playerId)
    local name = GetPlayerName(playerId)
    local plyPed = GetPlayerPed(playerId)
    local coords = GetEntityCoords(plyPed)

    print("Player " .. name .. " pressed panic button in coordinates " .. tostring(coords))
end)
```
