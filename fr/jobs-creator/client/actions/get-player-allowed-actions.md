---
title: "Get player allowed actions"
description: "Récupère la liste des actions que le job actuel du joueur est autorisé à effectuer."
icon: "list-check"
---

Récupère les actions autorisées à partir du job du joueur.

<CodeGroup>

```lua Export
exports["jobs_creator"]:getAllowedActions()
```

```lua Example
local actions = exports["jobs_creator"]:getAllowedActions()
print(ESX.DumpTable(actions))
--[[
    Example output

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

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `actions` | table | Table clé-valeur où la clé est l'action et la valeur est un booléen indiquant si elle est autorisée ou non |
