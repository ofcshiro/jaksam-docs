---
title: "Ouvrir le menu manuellement"
description: "Déclenche l'ouverture du menu de Blips Creator depuis ton propre code côté client."
icon: "map-location-dot"
---

Tu peux utiliser cet event depuis n'importe où **côté client** pour ouvrir le menu.

```lua Event
TriggerEvent("blips_creator:openBlipsMenu")
```

## Exemple

Tu peux ouvrir le menu avec une commande, par exemple :

```lua
RegisterCommand("blipscreator", function()
    TriggerEvent("blips_creator:openBlipsMenu")
end)
```
