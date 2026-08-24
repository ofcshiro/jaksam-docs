---
title: "Add item to trunk"
description: "Ajoute des objets au coffre d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire."
icon: "car-side"
---

Ajoute des objets au coffre d'un véhicule en utilisant uniquement la plaque d'immatriculation, en résolvant automatiquement l'ID complet de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:addItemToTrunk(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Ajoute 5 bouteilles d'eau au coffre du véhicule
local plate = GetVehicleNumberPlateText(vehicle)
local success, result = exports['jaksam_inventory']:addItemToTrunk(plate, 'water', 5)

if not success then
    print("Failed to add item: " .. result)
end

-- Ajoute un objet avec des métadonnées
local success = exports['jaksam_inventory']:addItemToTrunk("ABC 123", 'phone', 1, {
    number = "555-0123"
})
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
- Crée automatiquement l'inventaire du coffre s'il n'existe pas
- Pour les véhicules possédés, l'inventaire est persistant (enregistré en base de données)
