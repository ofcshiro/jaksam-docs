---
title: "Item removed"
description: "Hook déclenché quand un item est retiré d'un inventaire."
icon: "circle-minus"
---

Se déclenche quand un item est retiré d'un inventaire. Enregistre-le avec [`registerHook`](/fr/jaksam-inventory/hooks#enregistrer-un-hook) en utilisant le nom d'event `onItemRemoved`.

### Payload

| Champ | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string | par exemple `"player:1"` |
| `itemName` | string | par exemple `"bread"` |
| `amount` | number | Quantité retirée |
| `metadata` | table \| nil | Métadonnées de l'item |
| `slotId` | number | Slot depuis lequel l'item a été retiré |

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] Le contenu source ne comportait pas d'exemple dédié pour ce hook spécifique. Voir [l'aperçu des Hooks](/fr/jaksam-inventory/hooks) pour le modèle général de `registerHook` et ses filtres, qui s'appliquent de la même façon ici.
</Info>
