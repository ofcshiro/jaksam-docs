---
title: "Pocket crafting finished"
description: "Se activa del lado del servidor cuando un jugador completa un proceso de pocket crafting."
icon: "flask-vial"
---

Este event se activa después de que un jugador complete con éxito un proceso de pocket crafting. Se dispara justo después de que el jugador reciba su item crafteado.

```lua Event
AddEventHandler("drugs_creator:pocketCraftingFinished", function(playerId, itemName)

end)
```

### Parámetros

| Nombre        | Tipo de dato | Descripción                                                  |
| ----------- | --------- | ------------------------------------------------------------- |
| `playerId`  | integer   | El ID de servidor del jugador que completó el crafteo            |
| `itemName`  | string    | El nombre del item de pocket crafting que se usó                 |

## Ejemplo

```lua
AddEventHandler("drugs_creator:pocketCraftingFinished", function(playerId, itemName)
    print("Player " .. playerId .. " finished crafting with " .. itemName)
end)
```
