---
title: "Hide action button"
description: "Oculta un botón de acción de la interfaz del inventario sin eliminarlo."
icon: "eye-slash"
---

Oculta un botón de acción de la interfaz del inventario sin eliminarlo.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:hideActionButton(id)
```

```lua Example
-- Oculta un botón temporalmente
exports['jaksam_inventory']:hideActionButton('police_actions')

-- Oculta el botón cuando el jugador está fuera de servicio
AddEventHandler('esx:setJob', function(job)
    if job.name ~= 'police' then
        exports['jaksam_inventory']:hideActionButton('police_actions')
    end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `id` | string | El identificador único del botón a ocultar |

### Valor de retorno

Ninguno.
