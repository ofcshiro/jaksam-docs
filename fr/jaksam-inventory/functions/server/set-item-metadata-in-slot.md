---
title: "Set item metadata in slot"
description: "Met à jour les métadonnées d'un item dans un slot d'inventaire spécifique."
icon: "grid-2"
---

Met à jour les métadonnées d'un item dans un slot d'inventaire spécifique.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setItemMetadataInSlot(inventoryId, slotId, metadata)
```

```lua Example
-- Met à jour les munitions de l'arme
exports['jaksam_inventory']:setItemMetadataInSlot(1, 5, {
    serial = "ABC123",
    ammo = 6 -- met à jour le nombre de munitions
})

-- Met à jour la durabilité de l'item
exports['jaksam_inventory']:setItemMetadataInSlot(1, 3, {
    durability = 50
})
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire contenant l'item |
| `slotId` | number | Le slot contenant l'item à mettre à jour |
| `metadata` | table | Les nouvelles métadonnées à définir |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si les métadonnées ont été mises à jour avec succès |
| `resultCode` | string | Message d'erreur si l'opération a échoué |
