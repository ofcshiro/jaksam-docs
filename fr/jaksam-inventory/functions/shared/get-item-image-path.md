---
title: "Get item image path"
description: "Récupère le chemin d'image NUI d'un item, avec un repli vers une image par défaut si aucune n'est trouvée."
icon: "image"
---

Récupère le chemin d'image NUI d'un item. La fonction utilise un système de repli : elle vérifie d'abord si l'item a un champ `image` personnalisé, puis essaie de trouver des fichiers `.png` ou `.webp`, et enfin se rabat sur l'image par défaut `box.webp`.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemImagePath(itemName)
```

```lua Example
local imagePath = exports['jaksam_inventory']:getItemImagePath('bread')
print(imagePath) -- nui://jaksam_inventory/_images/bread.png

-- Item avec un champ image personnalisé
local customImage = exports['jaksam_inventory']:getItemImagePath('custom_item')
print(customImage) -- nui://jaksam_inventory/_images/custom_image.png (si item.image est défini)

-- Item non trouvé retourne l'image box par défaut
local notFound = exports['jaksam_inventory']:getItemImagePath('invalid_item')
print(notFound) -- nui://jaksam_inventory/_images/box.webp
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom de l'item dont récupérer le chemin d'image |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `imagePath` | string | Le chemin d'image NUI (par exemple "nui://jaksam_inventory/_images/bread.png"). Retourne toujours un chemin valide, avec repli vers `box.webp` si l'item n'existe pas ou si aucune image n'est trouvée |
