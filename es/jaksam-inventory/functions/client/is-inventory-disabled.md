---
title: "Is inventory disabled"
description: "Devuelve si la apertura del inventario está actualmente deshabilitada."
icon: "ban"
---

Devuelve si la apertura del inventario está actualmente deshabilitada.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:isInventoryDisabled()
```

```lua Example
-- Comprueba si el inventario está deshabilitado antes de hacer algo
local disabled = exports['jaksam_inventory']:isInventoryDisabled()

if disabled then
    print('Inventory is currently disabled')
end

-- Protege una acción personalizada
if not exports['jaksam_inventory']:isInventoryDisabled() then
    exports['jaksam_inventory']:openInventory('my_stash')
end
```

</CodeGroup>

### Parámetros

Ninguno.

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `disabled` | boolean | True si la apertura del inventario está actualmente deshabilitada, false en caso contrario |
