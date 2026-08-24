---
title: "Add item"
description: "Ajoute des objets à un inventaire avec prise en charge des métadonnées et du placement dans un emplacement spécifique."
icon: "cube"
---

Ajoute des objets à un inventaire avec prise en charge des métadonnées et du placement dans un emplacement spécifique.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:addItem(inventoryId, itemName, amount, metadata, slotId)
```

```lua Example
-- Ajoute 5 pains à l'inventaire d'un joueur
local success, result = exports['jaksam_inventory']:addItem(1, 'bread', 5)

-- Ajoute une arme avec des métadonnées
local success, result = exports['jaksam_inventory']:addItem(1, 'WEAPON_PISTOL', 1, {
    serial = "ABC123",
    ammo = 12
})

-- Ajoute un objet dans un emplacement spécifique
local success, result = exports['jaksam_inventory']:addItem(1, 'bread', 1, nil, 5) -- emplacement 5
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire auquel ajouter des objets. Peut être l'ID serveur d'un joueur ou un ID d'inventaire |
| `itemName` | string | Le nom de l'objet à ajouter |
| `amount` | number | Le nombre d'objets à ajouter |
| `metadata` | table | Données supplémentaires pour l'objet (ex. : numéro de série d'une arme, durabilité de l'objet) |
| `slotId` | number | Emplacement spécifique où placer l'objet |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si les objets ont été ajoutés avec succès |
| `resultCode` | string | Message d'erreur si l'opération a échoué |
