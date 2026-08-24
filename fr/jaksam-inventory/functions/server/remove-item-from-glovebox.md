---
title: "Remove item from glovebox"
description: "Retire des objets de la boîte à gants d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire."
icon: "car"
---

Retire des objets de la boîte à gants d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:removeItemFromGlovebox(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Retire des documents de la boîte à gants
local plate = GetVehicleNumberPlateText(vehicle)
local success = exports['jaksam_inventory']:removeItemFromGlovebox(plate, 'documents', 1)

if not success then
    print("Document not found in glovebox")
end
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
