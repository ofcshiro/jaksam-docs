---
title: "Add item to glovebox"
description: "Ajoute des objets à la boîte à gants d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire."
icon: "car"
---

Ajoute des objets à la boîte à gants d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:addItemToGlovebox(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Ajoute des documents à la boîte à gants
local plate = GetVehicleNumberPlateText(vehicle)
local success = exports['jaksam_inventory']:addItemToGlovebox(plate, 'documents', 1)

-- Ajoute plusieurs objets
local success = exports['jaksam_inventory']:addItemToGlovebox("XYZ 789", 'money', 500)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `plate` | string | La plaque d'immatriculation du véhicule |
| `itemName` | string | Le nom de l'objet à ajouter |
| `amount` | number | Le nombre d'objets à ajouter |
| `metadata` | table | Données supplémentaires pour l'objet |
| `slotId` | number | Emplacement spécifique où placer l'objet |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si les objets ont été ajoutés avec succès |
| `resultCode` | string | Message d'erreur si l'opération a échoué (ex. : "vehicle_not_found") |
| `notificationType` | string | Type de notification à afficher à l'utilisateur |

### Notes

- Fonctionne avec les véhicules possédés (même s'ils ne sont pas apparus/au garage)
- Fonctionne avec les véhicules PNJ (s'ils sont actuellement apparus)
- Crée automatiquement l'inventaire de la boîte à gants s'il n'existe pas
- Pour les véhicules possédés, l'inventaire est persistant (enregistré en base de données)
