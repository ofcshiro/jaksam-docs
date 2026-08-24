---
title: "Set weapon wheel"
description: "Habilita o deshabilita la rueda de armas predeterminada de GTA5 y los ajustes de armas relacionados. Útil para minijuegos."
icon: "circle-dot"
---

Habilita o deshabilita la rueda de armas y los ajustes de armas relacionados. Útil para minijuegos en los que quieras usar la rueda de armas de GTA 5.

<Warning>
  Esta función impedirá usar armas del inventario, está pensada principalmente para minijuegos FFA.
</Warning>

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setWeaponWheel(state)
```

```lua Example
-- Deshabilita la rueda de armas de GTA5 (modo predeterminado de jaksam_inventory)
exports['jaksam_inventory']:setWeaponWheel(false)

-- Habilita la rueda de armas de GTA5 (habilítala solo para minijuegos)
exports['jaksam_inventory']:setWeaponWheel(true)

-- Habilita la rueda de armas predeterminada de GTA 5 durante un minijuego FFA
exports['jaksam_inventory']:setWeaponWheel(true)
-- ... código del minijuego ...
exports['jaksam_inventory']:setWeaponWheel(false) -- Deshabilita de nuevo la rueda de GTA5, volviendo al modo normal de jaksam_inventory
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `state` | boolean \| nil | Si es true, se habilitará la rueda de armas predeterminada de GTA5 y las armas NO serán gestionadas por jaksam inventory. Si es false, se deshabilitará la rueda de armas predeterminada de GTA5 y las armas SÍ serán gestionadas por jaksam inventory. Si es nil, usa el estado interno actual |

### Valor de retorno

Ninguno. Desequipa automáticamente el arma actual al ser llamada.
