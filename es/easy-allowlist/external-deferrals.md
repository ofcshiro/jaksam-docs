---
title: "External deferrals"
description: "Integra la queue de Easy Allowlist con un framework que ya usa sus propios connection deferrals, como el connectqueue de QBCore."
icon: "code-merge"
---

### Ejemplo para QB-Core

**Código antiguo**

```lua
-- Ruta: qb-core/server/events.lua

local function OnPlayerConnecting(name, setKickReason, deferrals)
    local player = source
    local license
    local identifiers = GetPlayerIdentifiers(player)
    deferrals.defer()

    -- espera obligatoria!
    Wait(0)

    deferrals.update(string.format('Hello %s. Validating Your Rockstar License', name))

    for _, v in pairs(identifiers) do
        if string.find(v, 'license') then
            license = v
            break
        end
    end

    -- espera obligatoria!
    Wait(2500)

    deferrals.update(string.format('Hello %s. We are checking if you are banned.', name))

    local isBanned, Reason = QBCore.Functions.IsPlayerBanned(player)
    local isLicenseAlreadyInUse = QBCore.Functions.IsLicenseInUse(license)

    Wait(2500)

    deferrals.update(string.format('Welcome %s to {Server Name}.', name))

    if not license then
        deferrals.done('No Valid Rockstar License Found')
    elseif isBanned then
        deferrals.done(Reason)
    elseif isLicenseAlreadyInUse then
        deferrals.done('Duplicate Rockstar License Found')
    else
        deferrals.done()
        Wait(1000)
        TriggerEvent('connectqueue:playerConnect', name, setKickReason, deferrals)
    end
end
```

**Código nuevo**

```lua
-- Ruta: qb-core/server/events.lua

local function OnPlayerConnecting(name, setKickReason, deferrals)
    local player = source
    local license
    local identifiers = GetPlayerIdentifiers(player)
    deferrals.defer()

    -- espera obligatoria!
    Wait(0)

    deferrals.update(string.format('Hello %s. Validating Your Rockstar License', name))

    for _, v in pairs(identifiers) do
        if string.find(v, 'license') then
            license = v
            break
        end
    end

    -- espera obligatoria!
    Wait(2500)

    deferrals.update(string.format('Hello %s. We are checking if you are banned.', name))

    local isBanned, Reason = QBCore.Functions.IsPlayerBanned(player)
    local isLicenseAlreadyInUse = QBCore.Functions.IsLicenseInUse(license)

    Wait(2500)

    deferrals.update(string.format('Welcome %s to {Server Name}.', name))

    if not license then
        deferrals.done('No Valid Rockstar License Found')
    elseif isBanned then
        deferrals.done(Reason)
    elseif isLicenseAlreadyInUse then
        deferrals.done('Duplicate Rockstar License Found')
    else
        --[[
            Wait(1000)
            TriggerEvent('connectqueue:playerConnect', name, setKickReason, deferrals)
        ]]

        deferrals.done()
    end
end
```

### Desactivar la queue por defecto de QB-Core

Para desactivar la queue por defecto de QB-Core, elimina la carpeta del script `connectqueue` y quita la dependencia en el script qb-core.

**Ruta de ejemplo: `qb-core/fxmanifest.lua`**

```lua
-- CÓDIGO ANTIGUO
dependencies {
	'oxmysql',
	'progressbar',
	'connectqueue'
}
```

```lua
-- CÓDIGO NUEVO
dependencies {
	'oxmysql',
	'progressbar'
}
```
