---
title: "Has item"
description: "Vérifie si un inventaire contient un objet spécifique."
icon: "circle-check"
---

Vérifie si un inventaire contient un objet spécifique.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:hasItem(inventoryId, itemName, quantity)
```

```lua Example
-- Vérifie si le joueur a 5 pains
local hasItem = exports['jaksam_inventory']:hasItem(1, 'bread', 5)

if hasItem then
    -- Il est sûr de retirer les objets
    exports['jaksam_inventory']:removeItem(1, 'bread', 5)
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à vérifier |
| `itemName` | string | Le nom de l'objet à vérifier |
| `quantity` | number | Le nombre d'objets à vérifier. Par défaut : 1 |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `boolean` | boolean | True si l'inventaire contient l'objet, false sinon |
