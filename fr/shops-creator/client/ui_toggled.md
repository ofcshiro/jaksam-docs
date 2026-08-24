---
title: "UI activée/désactivée"
description: "Masque ou affiche ta propre interface quand l'UI de la boutique est activée/désactivée."
icon: "eye"
---

Utile pour masquer/afficher ton interface quand l'UI de la boutique est activée/désactivée.

## UI de la boutique activée

```lua
RegisterNetEvent("shops_creator:ui:show", function()
    -- Désactive ton interface ici avec ton propre code
end)
```

## UI de la boutique désactivée

```lua
RegisterNetEvent("shops_creator:ui:hide", function()
    -- Active ton interface ici avec ton propre code
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
