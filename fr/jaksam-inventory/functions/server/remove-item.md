---
title: "Remove item"
description: "Retire des objets d'un inventaire."
icon: "trash"
---

Retire des objets d'un inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:removeItem(inventoryId, itemName, amount, metadata, slotId)
```

```lua Example
-- Retire 5 pains de l'inventaire du joueur
local success, result = exports['jaksam_inventory']:removeItem(1, 'bread', 5)

-- Retire une arme spécifique par métadonnées
local success, result = exports['jaksam_inventory']:removeItem(1, 'weapon_pistol', 1, {
    serial = "ABC123"
})

-- Retire depuis un emplacement spécifique
local success, result = exports['jaksam_inventory']:removeItem(1, 'bread', 1, nil, 5)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire duquel retirer des objets. Peut être l'ID serveur d'un joueur ou un ID d'inventaire |
| `itemName` | string | Le nom de l'objet à retirer |
| `amount` | number | Le nombre d'objets à retirer |
| `metadata` | table | Métadonnées à faire correspondre lors du retrait (si fourni, seuls les objets avec les mêmes métadonnées ET le même nom seront retirés) |
| `slotId` | number | Emplacement spécifique duquel retirer les objets |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si les objets ont été retirés avec succès |
| `resultCode` | string | Message d'erreur si l'opération a échoué |
