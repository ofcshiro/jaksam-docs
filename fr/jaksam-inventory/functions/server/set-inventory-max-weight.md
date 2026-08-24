---
title: "Set inventory max weight"
description: "Définit la capacité de poids maximale d'un inventaire."
icon: "weight-hanging"
---

Définit la capacité de poids maximale d'un inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setInventoryMaxWeight(inventoryId, maxWeight)
```

```lua Example
-- Définit le poids max de l'inventaire d'un joueur
exports['jaksam_inventory']:setInventoryMaxWeight(1, 100)

-- Définit le poids max d'une planque
exports['jaksam_inventory']:setInventoryMaxWeight('police_stash_1', 500)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à modifier |
| `maxWeight` | number | La nouvelle capacité de poids maximale |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si le poids a été défini avec succès |
