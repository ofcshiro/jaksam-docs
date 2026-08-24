---
title: "Save dirty inventories"
description: "Guarda todos los inventarios modificados en la base de datos."
icon: "floppy-disk"
---

Guarda todos los inventarios modificados en la base de datos.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:saveDirtyInventories()
```

```lua Example
-- Guarda todos los inventarios modificados
exports['jaksam_inventory']:saveDirtyInventories()

-- Buena práctica: guardar antes de reiniciar el servidor
AddEventHandler('onResourceStop', function(resourceName)
    if resourceName == GetCurrentResourceName() then
        exports['jaksam_inventory']:saveDirtyInventories()
    end
end)
```

</CodeGroup>

### Parámetros

Ninguno.

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si todos los inventarios se guardaron correctamente |
