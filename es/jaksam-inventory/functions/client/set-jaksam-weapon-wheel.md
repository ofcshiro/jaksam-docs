---
title: "Set jaksam weapon wheel"
description: "Habilita o deshabilita la rueda de armas radial personalizada de jaksam en tiempo de ejecución."
icon: "circle-dot"
---

Habilita o deshabilita la rueda de armas radial personalizada de jaksam en tiempo de ejecución. Útil cuando necesitas evitar que los jugadores cambien de arma mediante la rueda radial durante escenarios específicos (cutscenes, minijuegos, etc.).

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setJaksamWeaponWheel(state)
```

```lua Example
-- Deshabilita la rueda de armas de jaksam durante una cutscene
exports['jaksam_inventory']:setJaksamWeaponWheel(false)
-- ... código de la cutscene ...
exports['jaksam_inventory']:setJaksamWeaponWheel(true) -- Vuelve a habilitarla después
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `state` | boolean \| nil | Si es true, se habilita la rueda de armas radial de jaksam. Si es false, se deshabilita la rueda de armas radial de jaksam (la cierra de inmediato si está abierta). Si es nil, usa el estado interno actual |

### Valor de retorno

Ninguno.
