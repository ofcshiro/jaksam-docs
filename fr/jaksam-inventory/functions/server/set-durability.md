---
title: "Set durability"
description: "Définit la valeur de durabilité d'un item dans un slot d'inventaire spécifique."
icon: "gauge"
---

Définit la valeur de durabilité d'un item dans un slot d'inventaire spécifique.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setDurability(inventoryId, slotId, durability)
```

```lua Example
-- Définit la durabilité de l'arme à 75%
local success, result = exports['jaksam_inventory']:setDurability(1, 5, 75)

-- Diminue la durabilité après utilisation de l'arme
local item = exports['jaksam_inventory']:getItemFromSlot(playerId, slotId)
if item and item.metadata.durability then
    local newDurability = math.max(0, item.metadata.durability - 5)
    exports['jaksam_inventory']:setDurability(playerId, slotId, newDurability)
end

-- Définit la durabilité pour un item de planque
exports['jaksam_inventory']:setDurability('police_stash_1', 3, 100)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire contenant l'item. Peut être un server ID de joueur ou un ID d'inventaire |
| `slotId` | number | Le slot contenant l'item à mettre à jour |
| `durability` | number | La valeur de durabilité à définir (sera limitée entre 0 et 100) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si la durabilité a été mise à jour avec succès |
| `resultCode` | string | Message d'erreur si l'opération a échoué |
