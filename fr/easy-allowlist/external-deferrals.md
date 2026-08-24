---
title: "Deferrals externes"
description: "Intègre la queue d'Easy Allowlist à un framework qui utilise déjà ses propres deferrals de connexion, comme le connectqueue de QBCore."
icon: "code-merge"
---

### Exemple pour QB-Core

**Ancien code**

```lua
-- Chemin : qb-core/server/events.lua

local function OnPlayerConnecting(name, setKickReason, deferrals)
    local player = source
    local license
    local identifiers = GetPlayerIdentifiers(player)
    deferrals.defer()

    -- attente obligatoire !
    Wait(0)

    deferrals.update(string.format('Hello %s. Validating Your Rockstar License', name))

    for _, v in pairs(identifiers) do
        if string.find(v, 'license') then
            license = v
            break
        end
    end

    -- attente obligatoire !
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

**Nouveau code**

```lua
-- Chemin : qb-core/server/events.lua

local function OnPlayerConnecting(name, setKickReason, deferrals)
    local player = source
    local license
    local identifiers = GetPlayerIdentifiers(player)
    deferrals.defer()

    -- attente obligatoire !
    Wait(0)

    deferrals.update(string.format('Hello %s. Validating Your Rockstar License', name))

    for _, v in pairs(identifiers) do
        if string.find(v, 'license') then
            license = v
            break
        end
    end

    -- attente obligatoire !
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

### Désactiver la queue par défaut de QB-Core

Pour désactiver la queue par défaut de QB-Core, supprime le dossier du script `connectqueue` et retire la dépendance dans le script qb-core.

**Exemple de chemin : `qb-core/fxmanifest.lua`**

```lua
-- ANCIEN CODE
dependencies {
	'oxmysql',
	'progressbar',
	'connectqueue'
}
```

```lua
-- NOUVEAU CODE
dependencies {
	'oxmysql',
	'progressbar'
}
```
