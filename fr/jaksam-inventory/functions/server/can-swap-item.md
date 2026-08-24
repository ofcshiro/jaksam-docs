---
title: "Can swap item"
description: "Vérifie s'il est possible d'échanger un objet contre un autre dans un inventaire."
icon: "right-left"
---

Vérifie si échanger firstItem (en retirant firstItemCount) contre testItem (en ajoutant testItemCount) est possible.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:canSwapItem(inventoryId, firstItem, firstItemCount, testItem, testItemCount)
```

```lua Example
-- Vérifie si le joueur peut échanger 5 pains contre 1 eau
local playerId = 1
local canSwap = exports['jaksam_inventory']:canSwapItem(playerId, 'bread', 5, 'water', 1)

if canSwap then
    exports['jaksam_inventory']:removeItem(playerId, 'bread', 5)
    exports['jaksam_inventory']:addItem(playerId, 'water', 1)
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à vérifier. Peut être l'ID serveur d'un joueur ou un ID d'inventaire |
| `firstItem` | string | Le nom de l'objet à vérifier |
| `firstItemCount` | number | Le nombre d'objets à retirer |
| `testItem` | string | Le nom de l'objet à ajouter |
| `testItemCount` | number | Le nombre d'objets à ajouter |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `boolean` | boolean | True si l'inventaire peut échanger les objets, false si l'échange n'est pas possible |
