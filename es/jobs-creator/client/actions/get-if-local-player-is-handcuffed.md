---
title: "Get if local player is handcuffed"
description: "Comprueba si el jugador local está esposado actualmente."
icon: "handcuffs"
---

Devuelve si el cliente/jugador **local** está esposado.

<CodeGroup>

```lua Export
exports["jobs_creator"]:isPlayerHandcuffed()
```

```lua Example
-- Este código comprueba continuamente si el jugador local (uno mismo) está esposado
-- Si es así, se desactivarán los controles indicados
Citizen.CreateThread(function()
    while true do
        Citizen.Wait(0)

        if(exports["jobs_creator"]:isPlayerHandcuffed())then
            DisableControlAction(0, 22, true) -- Desactiva el salto
        end
    end
end)
```

</CodeGroup>

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isHandcuffed` | boolean | `true` si el jugador está esposado, `false` si el jugador **no** está esposado |

### ¿Dónde insertar el código?

Puedes colocar el código en cualquier archivo del cliente de tus scripts.
