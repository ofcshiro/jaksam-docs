---
title: "Toggle icon display"
description: "Affiche ou cache les icônes/textes de toutes les portes."
icon: "eye"
---

Bascule l'affichage des icônes/textes de toutes les portes.

```lua Export
exports["doors_creator"]:toggleIconDisplay(newState)
```

### Paramètres

| Nom       | Type de donnée | Description                                          |
| ---------- | --------- | ----------------------------------------------------- |
| `newState` | boolean   | `true` = affiche l'icône/le texte, `false` = cache l'icône/le texte   |

## Exemple

```lua
RegisterCommand("hideDoorsIcon", function()
    exports["doors_creator"]:toggleIconDisplay(false)
end)
```
