---
title: "Can carry item"
description: "Vérifie si un inventaire a de la place pour des objets supplémentaires, en tenant compte à la fois du poids et des limites d'emplacements."
icon: "weight-hanging"
---

Vérifie si un inventaire a de la place pour des objets supplémentaires, en tenant compte à la fois du poids et des limites d'emplacements.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:canCarryItem(inventoryId, itemName, amount)
```

```lua Example
-- Vérifie si le joueur peut porter 5 pains
local canCarry = exports['jaksam_inventory']:canCarryItem(1, 'bread', 5)

if canCarry then
    -- Il est sûr d'ajouter les objets
    exports['jaksam_inventory']:addItem(1, 'bread', 5)
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à vérifier. Peut être l'ID serveur d'un joueur ou un ID d'inventaire |
| `itemName` | string | Le nom de l'objet à vérifier |
| `amount` | number | Le nombre d'objets à vérifier |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `boolean` | boolean | True si l'inventaire peut porter les objets, false si l'ajout dépasserait les limites de poids ou d'emplacements |
