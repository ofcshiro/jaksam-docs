---
title: "Set weapon wheel"
description: "Active ou désactive la roue d'armes par défaut de GTA5 et les paramètres d'armes associés. Utile pour les minijeux."
icon: "circle-dot"
---

Active ou désactive la roue d'armes et les paramètres d'armes associés. Utile pour les minijeux où tu veux la roue d'armes de GTA 5.

<Warning>
  Cette fonction empêche l'utilisation des armes depuis l'inventaire, elle est principalement destinée aux minijeux FFA.
</Warning>

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setWeaponWheel(state)
```

```lua Example
-- Désactive la roue d'armes de GTA5 (mode par défaut de jaksam_inventory)
exports['jaksam_inventory']:setWeaponWheel(false)

-- Active la roue d'armes de GTA5 (à activer uniquement pour les minijeux)
exports['jaksam_inventory']:setWeaponWheel(true)

-- Active la roue d'armes par défaut de GTA 5 pendant un minijeu FFA
exports['jaksam_inventory']:setWeaponWheel(true)
-- ... code du minijeu ...
exports['jaksam_inventory']:setWeaponWheel(false) -- Désactive à nouveau la roue GTA5, retour au mode normal de jaksam_inventory
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `state` | boolean \| nil | Si true, la roue d'armes par défaut de GTA5 sera activée et les armes NE seront PAS gérées par jaksam inventory. Si false, la roue d'armes par défaut de GTA5 sera désactivée et les armes SERONT gérées par jaksam inventory. Si nil, utilise l'état interne actuel |

### Valeur de retour

Aucune. Déséquipe automatiquement l'arme actuelle lors de l'appel.
