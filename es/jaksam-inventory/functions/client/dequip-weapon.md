---
title: "Dequip weapon"
description: "Desequipa el arma actualmente equipada."
icon: "gun"
---

Desequipa el arma actualmente equipada.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:dequipWeapon(skipSync)
```

```lua Example
-- Desequipa el arma
exports['jaksam_inventory']:dequipWeapon()

-- Desequipa el arma sin sincronizar la munición con el servidor
exports['jaksam_inventory']:dequipWeapon(true)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `skipSync` | boolean | Si es true, el arma se desequipará sin sincronizar la munición con el servidor |

### Valor de retorno

Ninguno. Desequipa el arma actualmente equipada.
