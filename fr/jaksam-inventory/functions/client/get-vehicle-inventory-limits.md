---
title: "Get vehicle inventory limits"
description: "Renvoie les limites du coffre ou de la boîte à gants pour un véhicule en fonction du modèle."
icon: "car"
---

Renvoie les limites du coffre ou de la boîte à gants pour un véhicule en fonction du modèle. Utilise la configuration de `_data/vehicles.lua` avec la priorité : `trunkByModel`/`gloveboxByModel` > `trunkByClass`/`gloveboxByClass`. Renvoie `0, 0` si le véhicule/la classe est configuré pour ne pas avoir de coffre/boîte à gants (`noTrunkVehicles`, `noTrunkClasses`, etc.)

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getVehicleInventoryLimits(vehicleModel, inventoryType)
```

```lua Example
local vehicle = GetVehiclePedIsIn(PlayerPedId(), false)
local maxSlots, maxWeight = exports['jaksam_inventory']:getVehicleInventoryLimits(GetEntityModel(vehicle), "trunk")

if maxWeight then
    print("Trunk max weight: " .. maxWeight)
else
    print("No specific config for this vehicle model/class")
end

-- Récupère les limites de la boîte à gants pour le véhicule 'adder'
local gloveboxSlots, gloveboxWeight = exports['jaksam_inventory']:getVehicleInventoryLimits('adder', "glovebox")
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicleModel` | number \| string | Le hash du modèle du véhicule (depuis `GetEntityModel`) ou le nom du modèle sous forme de string |
| `inventoryType` | string | Soit `"trunk"`, soit `"glovebox"` |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `maxSlots` | number \| nil | Le nombre maximum de slots pour l'inventaire du véhicule, ou nil si aucune configuration n'est trouvée |
| `maxWeight` | number \| nil | Le poids maximum pour l'inventaire du véhicule, ou nil si aucune configuration n'est trouvée |

### Notes

La documentation source signalait une virgule manquante entre `'adder'` et `"glovebox"` dans l'exemple d'origine, corrigée ici. À vérifier si ce bug était également présent dans le script sous-jacent lui-même.
