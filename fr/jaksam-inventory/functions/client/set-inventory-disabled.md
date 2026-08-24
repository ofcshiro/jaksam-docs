---
title: "Set inventory disabled"
description: "Désactive ou réactive entièrement l'ouverture de l'inventaire, en bloquant les hotkeys, les keybinds et les appels directs aux exports/événements."
icon: "ban"
---

Désactive ou réactive entièrement l'ouverture de l'inventaire. Quand elle est désactivée, toutes les interactions avec l'inventaire sont bloquées : hotkeys, keybinds et appels directs aux exports/événements. Si l'inventaire est actuellement ouvert au moment de la désactivation, il sera fermé et l'arme sera automatiquement déséquipée.

C'est utile pour les cinématiques, les minijeux, les barres de progression, ou tout scénario où le joueur ne doit pas pouvoir ouvrir l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setInventoryDisabled(disabled)
```

```lua Example
-- Désactive l'inventaire pendant une cinématique
exports['jaksam_inventory']:setInventoryDisabled(true)
-- ... code de la cinématique ...
exports['jaksam_inventory']:setInventoryDisabled(false)

-- Désactive l'inventaire pendant une barre de progression
exports['jaksam_inventory']:setInventoryDisabled(true)
-- ... logique de la barre de progression ...
exports['jaksam_inventory']:setInventoryDisabled(false)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `disabled` | boolean | Si true, l'ouverture de l'inventaire est entièrement bloquée. Si false, l'ouverture de l'inventaire est réactivée |

### Valeur de retour

Aucune.

### Notes

**Compatibilité ox_inventory :** Si tu migres depuis ox_inventory, cet export remplace le pattern du state bag `invBusy`. Les scripts qui font `LocalPlayer.state:set('invBusy', true, true)` continueront de fonctionner automatiquement, jaksam_inventory écoute les changements du state bag `invBusy` et les fait correspondre au même flag interne.

```lua
-- Pattern ox_inventory (fonctionne toujours avec jaksam_inventory)
LocalPlayer.state:set('invBusy', true, true)

-- Export natif jaksam_inventory (recommandé)
exports['jaksam_inventory']:setInventoryDisabled(true)
```
