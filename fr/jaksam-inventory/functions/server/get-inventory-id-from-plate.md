---
title: "Get inventory ID from plate"
description: "Résout l'ID complet de l'inventaire d'un compartiment de véhicule en utilisant uniquement la plaque d'immatriculation."
icon: "id-card"
---

Résout l'ID complet de l'inventaire d'un compartiment de véhicule en utilisant uniquement la plaque d'immatriculation.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getInventoryIdFromPlate(plate, compartment)
```

```lua Example
-- Récupère l'ID de l'inventaire du coffre
local plate = GetVehicleNumberPlateText(vehicle)
local trunkId = exports['jaksam_inventory']:getInventoryIdFromPlate(plate, "trunk")

if trunkId then
    print("Trunk ID: " .. trunkId)
    -- Tu peux maintenant utiliser les fonctions d'inventaire standard
    local inventory = exports['jaksam_inventory']:getInventory(trunkId)
end

-- Récupère l'ID de l'inventaire de la boîte à gants
local gloveboxId = exports['jaksam_inventory']:getInventoryIdFromPlate("ABC 123", "glovebox")
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `plate` | string | La plaque d'immatriculation du véhicule |
| `compartment` | string | Soit "trunk" soit "glovebox" |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| nil | L'ID complet de l'inventaire (format : `"vehicle:plate:model:compartment"`), nil si le véhicule n'est pas trouvé |

### Notes

Recherche dans cet ordre :

1. Base de données des véhicules possédés (ESX : `owned_vehicles`, QBCore : `player_vehicles`)
2. Inventaires existants dans la table `jaksam_inventory`
3. Véhicules actuellement apparus (`GetAllVehicles` - véhicules PNJ)

Pour les véhicules possédés, crée automatiquement l'inventaire s'il n'existe pas. Les inventaires créés sont persistants pour les véhicules possédés, temporaires pour les véhicules PNJ. Fonctionne même si le véhicule n'est pas actuellement apparu (au garage).
