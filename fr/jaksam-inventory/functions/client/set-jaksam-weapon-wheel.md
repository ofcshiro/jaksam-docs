---
title: "Set jaksam weapon wheel"
description: "Active ou désactive la roue d'armes radiale personnalisée de jaksam au runtime."
icon: "circle-dot"
---

Active ou désactive la roue d'armes radiale personnalisée de jaksam au runtime. Utile quand tu dois empêcher les joueurs de changer d'arme via la roue radiale pendant certains scénarios (cinématiques, minijeux, etc.).

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setJaksamWeaponWheel(state)
```

```lua Example
-- Désactive la roue d'armes jaksam pendant une cinématique
exports['jaksam_inventory']:setJaksamWeaponWheel(false)
-- ... code de la cinématique ...
exports['jaksam_inventory']:setJaksamWeaponWheel(true) -- Réactive ensuite
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `state` | boolean \| nil | Si true, la roue d'armes radiale jaksam est activée. Si false, la roue d'armes radiale jaksam est désactivée (la ferme immédiatement si elle est ouverte). Si nil, utilise l'état interne actuel |

### Valeur de retour

Aucune.
