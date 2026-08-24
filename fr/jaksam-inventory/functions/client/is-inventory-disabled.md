---
title: "Is inventory disabled"
description: "Renvoie si l'ouverture de l'inventaire est actuellement désactivée."
icon: "ban"
---

Renvoie si l'ouverture de l'inventaire est actuellement désactivée.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:isInventoryDisabled()
```

```lua Example
-- Vérifie si l'inventaire est désactivé avant de faire quelque chose
local disabled = exports['jaksam_inventory']:isInventoryDisabled()

if disabled then
    print('Inventory is currently disabled')
end

-- Protège une action personnalisée
if not exports['jaksam_inventory']:isInventoryDisabled() then
    exports['jaksam_inventory']:openInventory('my_stash')
end
```

</CodeGroup>

### Paramètres

Aucun.

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `disabled` | boolean | True si l'ouverture de l'inventaire est actuellement désactivée, false sinon |
