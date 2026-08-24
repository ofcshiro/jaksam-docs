---
title: "Show action button"
description: "Hace visible un botón de acción previamente oculto en la interfaz del inventario."
icon: "eye"
---

Hace visible un botón de acción previamente oculto en la interfaz del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:showActionButton(id)
```

```lua Example
-- Muestra un botón que se registró como oculto
exports['jaksam_inventory']:showActionButton('police_actions')

-- Muestra el botón cuando el jugador obtiene un trabajo específico
AddEventHandler('esx:setJob', function(job)
    if job.name == 'police' then
        exports['jaksam_inventory']:showActionButton('police_actions')
    end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `id` | string | El identificador único del botón a mostrar |

### Valor de retorno

Ninguno.
