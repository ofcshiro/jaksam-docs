---
title: "Remove item from trunk"
description: "Retire des objets du coffre d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire."
icon: "car-side"
---

Retire des objets du coffre d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:removeItemFromTrunk(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Retire 3 bouteilles d'eau du coffre
local plate = GetVehicleNumberPlateText(vehicle)
local success = exports['jaksam_inventory']:removeItemFromTrunk(plate, 'water', 3)

-- Retire depuis un emplacement spécifique
local success = exports['jaksam_inventory']:removeItemFromTrunk("ABC 123", 'weapon', 1, nil, 5)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `plate` | string | La plaque d'immatriculation du véhicule |
| `itemName` | string | Le nom de l'objet à retirer |
| `amount` | number | Le nombre d'objets à retirer |
| `metadata` | table | Métadonnées à faire correspondre pour le retrait (filtrage optionnel) |
| `slotId` | number | Emplacement spécifique d'où retirer l'objet |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si les objets ont été retirés avec succès |
| `resultCode` | string | Message d'erreur si l'opération a échoué |
| `notificationType` | string | Type de notification à afficher à l'utilisateur |

### Notes

Le véhicule doit exister (véhicule possédé en base de données ou véhicule PNJ actuellement apparu). Retourne false avec "vehicle_not_found" si le véhicule n'existe pas.
