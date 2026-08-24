---
title: "NPC accepted drug"
description: "Déclenché côté client après qu'un PNJ ait accepté une drogue, pour des animations personnalisées."
icon: "check"
---

Déclenché après qu'un PNJ ait accepté la drogue, afin que tu puisses créer ta propre animation personnalisée.

```lua Event
AddEventHandler("drugs_creator:npc:acceptedDrug", function(targetPedNetworkId)

end)
```

### Paramètres

| Nom                  | Type de donnée        | Description                                                    |
| ---------------------- | ----------------- | ------------------------------------------------------------------- |
| `targetPedNetworkId`   | ped network ID     | Le network ID du ped qui a accepté d'acheter la drogue           |

## Exemple

```lua
RegisterNetEvent("drugs_creator:framework:ready", function()
    -- Désactive les animations par défaut du script pour la vente aux NPC (sinon il y aurait 2 animations)
    exports["drugs_creator"]:disableScriptEvent("drugs_creator:npc:acceptedDrug")
end)

-- Nouvelle animation pour les NPC
RegisterNetEvent("drugs_creator:npc:acceptedDrug", function(targetPedNetworkId)
    local plyPed = PlayerPedId()
    local plyCoords = GetEntityCoords(plyPed)

    local targetPed = NetworkGetEntityFromNetworkId(targetPedNetworkId)
    local targetCoords = GetEntityCoords(targetPed)

    local animDict = "mp_common"
    local animName = "givetake1_b"

    while not HasAnimDictLoaded(animDict) do
        Citizen.Wait(0)
        RequestAnimDict(animDict)
    end

    local distance = #(targetCoords - plyCoords)

    if(distance < 1.5) then
        TaskPlayAnim(targetPed, animDict, animName, 4.0, -4.0, -1, 1, 0.0, false, false, false)

        Citizen.Wait(math.random(200, 500))

        TaskPlayAnim(plyPed, animDict, animName, 4.0, -4.0, -1, 1, 0.0, false, false, false)
    else
        local plyHeading = GetEntityHeading(plyPed)
        local netScene = CreateSynchronizedScene(plyCoords - vector3(0.0, 0.0, 1.0), vector3(0.0, 0.0, plyHeading), 2)
        local netSceneTarget = CreateSynchronizedScene(plyCoords - vector3(0.0, 0.0, 1.0), vector3(0.0, 0.0, plyHeading - 180.0), 2)

        TaskSynchronizedScene(plyPed, netScene, animDict, animName, 1.0, 1.0, -1, 1, 1.0, 0.0)
        TaskSynchronizedScene(targetPed, netSceneTarget, animDict, animName, 1.0, 1.0, -1, 1, 1.0, 0.0)

        SetSynchronizedSceneLooped(netScene, true)
        SetSynchronizedSceneLooped(netSceneTarget, true)
    end

    Citizen.Wait(config.npcSecondsToSell * 1000)

    ClearPedTasks(targetPed)
    ClearPedTasks(plyPed)
end)
```
