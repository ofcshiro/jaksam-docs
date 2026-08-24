---
title: "Get total item amount"
description: "Récupère la quantité totale d'un item spécifique dans l'inventaire du joueur."
icon: "hashtag"
---

Récupère la quantité totale d'un item spécifique dans l'inventaire du joueur.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getTotalItemAmount(itemName, metadata)
```

```lua Example
-- Récupère la quantité totale de pain
local breadCount = exports['jaksam_inventory']:getTotalItemAmount('bread')

-- Récupère la quantité d'une arme spécifique par numéro de série
local weaponCount = exports['jaksam_inventory']:getTotalItemAmount('weapon_pistol', {
    serial = "ABC123"
})
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom de l'item à compter |
| `metadata` | table | Metadata à comparer lors du comptage (si fourni, seuls les items ayant les mêmes metadata ET le même nom seront comptés) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `totalAmount` | number | Quantité totale de l'item dans l'inventaire du joueur |
