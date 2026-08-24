---
title: "Get total item amount"
description: "Retourne la quantité totale d'un objet spécifique dans un inventaire, y compris les objets dans les conteneurs."
icon: "hashtag"
---

Retourne la quantité totale d'un objet spécifique dans un inventaire, y compris les objets dans les conteneurs.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getTotalItemAmount(inventoryId, itemName, metadata, skipContainers)
```

```lua Example
-- Récupère la quantité totale de pain dans l'inventaire
local total = exports['jaksam_inventory']:getTotalItemAmount(1, 'bread')

-- Récupère la quantité avec des métadonnées spécifiques
local total = exports['jaksam_inventory']:getTotalItemAmount(1, 'weapon_pistol', {
    serial = "ABC123"
})

-- Récupère la quantité en excluant les conteneurs
local total, totalNoContainers = exports['jaksam_inventory']:getTotalItemAmount(1, 'bread', nil, true)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à vérifier |
| `itemName` | string | Le nom de l'objet à compter |
| `metadata` | table | Métadonnées à faire correspondre lors du comptage (si fourni, seuls les objets avec les mêmes métadonnées ET le même nom seront comptés) |
| `skipContainers` | boolean | Si true, les objets dans les conteneurs ne seront pas comptés |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `totalAmount` | number | Quantité totale de l'objet dans l'inventaire, conteneurs inclus (uniquement si skipContainers est false) |
| `totalAmountContainersExcluded` | number \| nil | Quantité totale en excluant les conteneurs (uniquement si skipContainers est false) |
