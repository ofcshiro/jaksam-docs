---
title: "Changer l'icône des portes"
description: "Personnalise la couleur, l'image et la taille de l'icône d'interaction des portes."
icon: "icons"
---

## Comment changer la couleur

Pour changer les couleurs de l'icône, édite le fichier `doors_creator/integrations/cl_integrations.lua` et modifie les lignes concernant la couleur :

```lua
-- r = rouge, g = vert, b = bleu, a = opacité
-- Toutes les valeurs vont de 0 à 255
-- Si toutes les couleurs sont réglées sur 255, l'image aura la couleur par défaut
color = {
    r = 50,
    g = 255,
    b = 50,
    a = 255,
}
```

## Comment changer l'icône/l'image

Pour changer l'icône/l'image, remplace simplement les images dans le dossier `doors_creator/icons/` — veille à utiliser exactement les mêmes noms.

## Comment changer la taille

L'échelle peut être modifiée directement dans le menu in-game, mais tu peux aussi ajuster les valeurs `x` et `y` si besoin dans le fichier `doors_creator/integrations/cl_integrations.lua` :

```lua
-- largeur de l'image
x = 0.03,

-- hauteur de l'image
y = 0.04,
```
