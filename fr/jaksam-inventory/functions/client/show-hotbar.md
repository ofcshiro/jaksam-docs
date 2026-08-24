---
title: "Show hotbar"
description: "Affiche l'interface de la hotbar avec les 5 premiers slots de l'inventaire du joueur."
icon: "grip"
---

Affiche l'interface de la hotbar avec les 5 premiers slots de l'inventaire du joueur.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:showHotbar()
```

```lua Example
-- Affiche la hotbar
exports['jaksam_inventory']:showHotbar()

-- Affiche la hotbar après réception d'un item
AddEventHandler('myScript:itemReceived', function()
    exports['jaksam_inventory']:showHotbar()
end)
```

</CodeGroup>

### Paramètres

Aucun.

### Valeur de retour

Aucune. Affiche l'interface de la hotbar qui se cache automatiquement après 2 secondes.

### Notes

- La hotbar affiche les slots 1 à 5 de l'inventaire du joueur
- Si `config.dynamicHotbar` est true, les slots vides à la fin sont cachés
- La hotbar se cache automatiquement après 2 secondes
- Plusieurs appels réinitialisent le minuteur de masquage
