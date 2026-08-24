---
title: "Get player allowed actions"
description: "Obtén la lista de acciones que el job actual del jugador tiene permitido realizar."
icon: "list-check"
---

Obtén las acciones permitidas del job del jugador.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getAllowedActions()
```

```lua Example
local actions = exports["jobs_creator"]:getAllowedActions()
print(ESX.DumpTable(actions))
--[[
    Ejemplo de salida

    {
        ["canHeal"] = false,
        ["canCheckDrivingLicense"] = false,
        ["canCheckWeaponLicense"] = false,
        ["canRevive"] = false,
        ["canCheckIdentity"] = false,
        ["canRepairVehicles"] = false,
        ["canHandcuff"] = true,
        ["enableBilling"] = true,
        ["canLockpickCars"] = false,
        ["canCheckVehicleOwner"] = false,
        ["canWashVehicles"] = false,
    }
]]
```

</CodeGroup>

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `actions` | table | Tabla clave-valor donde la clave es la acción y el valor es un boolean que indica si está permitida o no |
