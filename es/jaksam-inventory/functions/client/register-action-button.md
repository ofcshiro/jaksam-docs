---
title: "Register action button"
description: "Registra un botón de acción personalizado en la barra de herramientas de la interfaz del inventario."
icon: "square-plus"
---

Registra un botón de acción personalizado en la barra de herramientas de la interfaz del inventario. Los botones de acción aparecen en el lado derecho del inventario y pueden ejecutar cualquier lógica personalizada al hacer clic.

<Tip>
  Para una guía completa con imágenes y ejemplos, consulta la [Guía de botones de acción](/es/jaksam-inventory/guides/action-buttons).
</Tip>

<CodeGroup>

```lua Export
exports['jaksam_inventory']:registerActionButton(id, icon, tooltip, onClick, visible)
```

```lua Example
-- Registra un botón de acción simple
exports['jaksam_inventory']:registerActionButton(
    'my_custom_button',
    'bi-star-fill',
    'My Custom Action',
    function()
        print('Button clicked!')
        -- Tu lógica personalizada aquí
    end
)

-- Registra un botón oculto (para mostrarlo después según condiciones)
exports['jaksam_inventory']:registerActionButton(
    'police_actions',
    'bi-shield-check',
    'Police Actions',
    function()
        TriggerEvent('myPoliceScript:openMenu')
    end,
    false -- oculto por defecto
)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `id` | string | Identificador único del botón. Se usa para referenciar el botón al mostrarlo/ocultarlo/eliminar su registro |
| `icon` | string | Nombre de clase de Bootstrap Icons (por ejemplo, "bi-shield-x", "bi-car-front-fill"). Encuentra íconos en [icons.getbootstrap.com](https://icons.getbootstrap.com/) |
| `tooltip` | string \| nil | Texto del tooltip mostrado al pasar el cursor por el botón. Puede ser nil para no mostrar tooltip |
| `onClick` | function | Función de callback ejecutada al hacer clic en el botón |
| `visible` | boolean \| nil | Si el botón debe ser visible inicialmente. Por defecto: true |

### Valor de retorno

Ninguno.
