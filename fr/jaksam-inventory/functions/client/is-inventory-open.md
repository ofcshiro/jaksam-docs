---
title: "Is inventory open"
description: "Vérifie si un inventaire est actuellement ouvert."
icon: "door-open"
---

Vérifie si un inventaire est actuellement ouvert. Si aucun ID d'inventaire n'est fourni, renvoie si l'interface de l'inventaire est actuellement active (un inventaire quel qu'il soit est ouvert). Si un ID d'inventaire est fourni, vérifie si cet inventaire spécifique est ouvert.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:isInventoryOpen(inventoryId)
```

```lua Example
-- Vérifie si une interface d'inventaire quelconque est ouverte
local isAnyInventoryOpen = exports['jaksam_inventory']:isInventoryOpen()

if isAnyInventoryOpen then
    print('An inventory is currently open')
else
    print('No inventory is open')
end

-- Vérifie si un inventaire spécifique est ouvert
local isPoliceStashOpen = exports['jaksam_inventory']:isInventoryOpen('police_stash_1')

if isPoliceStashOpen then
    print('Police stash is currently open')
end

-- Empêche l'ouverture d'une autre interface si l'inventaire est déjà ouvert
if not exports['jaksam_inventory']:isInventoryOpen() then
    -- Ouvre une interface personnalisée
    TriggerEvent('myScript:openCustomUI')
else
    notify("Can't do it while inventory is open")
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| nil | L'ID de l'inventaire à vérifier. Si nil, renvoie si une interface d'inventaire quelconque est actuellement active |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isOpen` | boolean | True si l'inventaire (ou une interface d'inventaire quelconque quand inventoryId est nil) est ouvert, false sinon |
