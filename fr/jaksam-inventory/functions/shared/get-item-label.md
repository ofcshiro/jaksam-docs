---
title: "Get item label"
description: "Récupère uniquement le label (nom affiché) d'un item. Une alternative plus simple et plus rapide à getStaticItem quand tu n'as besoin que du label de l'item."
icon: "tag"
---

Récupère uniquement le label (nom affiché) d'un item. C'est une alternative plus simple et plus rapide à `getStaticItem` quand tu n'as besoin que du label de l'item.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemLabel(itemName)
```

```lua Example
local label = exports['jaksam_inventory']:getItemLabel('bread')
print(label) -- Bread

-- Item non trouvé retourne nil
local notFound = exports['jaksam_inventory']:getItemLabel('invalid_item')
print(notFound) -- nil
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom de l'item dont récupérer le label |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `label` | string \| nil | Le label (nom affiché) de l'item, ou nil si l'item n'est pas trouvé |
