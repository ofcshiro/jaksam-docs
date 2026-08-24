---
title: "Unregister action button"
description: "Elimina un botón de acción previamente registrado de la interfaz del inventario."
icon: "square-minus"
---

Elimina un botón de acción previamente registrado de la interfaz del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:unregisterActionButton(id)
```

```lua Example
-- Elimina el registro de un botón cuando ya no se necesita
exports['jaksam_inventory']:unregisterActionButton('my_custom_button')

-- Elimina el registro cuando el jugador deja un trabajo
AddEventHandler('esx:setJob', function(job)
    if job.name ~= 'police' then
        exports['jaksam_inventory']:unregisterActionButton('police_actions')
    end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `id` | string | El identificador único del botón a eliminar (el mismo id usado en `registerActionButton`) |

### Valor de retorno

Ninguno.
