---
title: "NPC accepted drug"
description: "Se activa del lado del cliente después de que un NPC acepte una droga, para animaciones personalizadas."
icon: "check"
---

Se activa después de que un NPC acepte la droga, para que puedas crear tu propia animación personalizada.

```lua Event
AddEventHandler("drugs_creator:npc:acceptedDrug", function(targetPedNetworkId)

end)
```

### Parámetros

| Nombre                  | Tipo de dato        | Descripción                                                    |
| ---------------------- | ----------------- | ------------------------------------------------------------------- |
| `targetPedNetworkId`   | ped network ID     | El network ID del ped que aceptó comprar la droga           |

## Ejemplo

```lua
RegisterNetEvent("drugs_creator:framework:ready", function()
    -- Desactiva las animaciones por defecto del script para la venta a NPCs (de lo contrario habría 2 animaciones)
    exports["drugs_creator"]:disableScriptEvent("drugs_creator:npc:acceptedDrug")
end)

-- Nueva animación para los NPCs
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
