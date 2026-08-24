---
title: "Get item label"
description: "Récupère le libellé affiché d'un objet."
icon: "tag"
---

Récupère le libellé affiché d'un objet.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemLabel(itemName)
```

```lua Example
-- Récupère le libellé d'un objet
local label = exports['jaksam_inventory']:getItemLabel('bread')
print(label) -- affiche "Bread" ou le libellé défini

-- Vérifie si un objet existe en utilisant le libellé (bien que cela fonctionne, la meilleure façon serait d'utiliser getStaticItem)
if not exports['jaksam_inventory']:getItemLabel('invalid_item') then
    print('Item does not exist')
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom de l'objet pour lequel récupérer le libellé |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `label` | string \| nil | Le libellé affiché de l'objet, nil si l'objet n'existe pas |
