---
title: "Empêcher le vol des armes de police"
icon: "user-shield"
description: "Restreint certaines armes pour que seuls les joueurs avec le job police puissent les déplacer dans leur inventaire"
---

Tu veux t'assurer que seuls les policiers peuvent déplacer les armes de police vers leur inventaire ? Ce guide te montre comment faire, étape par étape.

Cette fonctionnalité empêche les joueurs qui ne sont pas policiers de déplacer des armes de police vers leur inventaire personnel. Si un joueur essaie de voler une arme de police, il recevra un message d'erreur et le transfert sera bloqué.

<Note>
  Cette fonctionnalité est fournie automatiquement par le hook `_hooks/sv_policeonly.lua` (au cas où tu voudrais le modifier). Tu dois juste marquer tes armes comme réservées à la police.
</Note>

## Guide étape par étape

<Steps>
  <Step title="Ouvre le fichier des items">
    Ouvre les fichiers de ton serveur et va dans : `jaksam_inventory/_data/items.lua`
  </Step>
  <Step title="Trouve ou crée l'arme">
    Trouve l'item d'arme que tu veux protéger (ou crée-le s'il n'existe pas).
  </Step>
  <Step title="Marque-la comme réservée à la police">
    Ajoute `policeOnly = true` à la définition de l'item.
  </Step>
  <Step title="Redémarre">
    Sauvegarde le fichier et redémarre le script/recharge le serveur.
  </Step>
</Steps>

<Tip>
  C'est tout ! Maintenant, seuls les joueurs avec le job "police" peuvent déplacer cette arme vers leur inventaire personnel.
</Tip>

## Exemples

### Exemple 1 : Combat Pistol

```lua
['WEAPON_COMBATPISTOL'] = {
    label = 'Combat Pistol',
    weight = 1.0,
    stackable = false,
    close = true,
    description = 'A combat pistol',
    type = 'weapon',
    ammo = 'ammo_9mm',
    throwableOptions = {
        model = nil,
        coords = {x = 0.08, y = 0.03, z = -0.06},
        rot = {x = -25.45, y = -3.76, z = 49.99}
    },
    policeOnly = true  -- Seule la police peut déplacer cette arme
},
```

### Exemple 2 : Stun Gun

```lua
['WEAPON_STUNGUN'] = {
    label = 'Stun Gun',
    weight = 1.0,
    stackable = false,
    close = true,
    description = 'A police stun gun',
    type = 'weapon',
    policeOnly = true  -- Seule la police peut déplacer cette arme
},
```

## Comment ça marche

Le hook `sv_policeonly.lua` vérifie automatiquement chaque fois que quelqu'un essaie de déplacer une arme avec `policeOnly = true` vers un inventaire de joueur. Si le joueur n'a pas le job "police", le transfert est bloqué et il voit un message d'erreur.

<Warning>
  Ceci bloque uniquement les transferts vers les **inventaires de joueurs**. Les armes de police peuvent toujours être déplacées entre les autres types d'inventaires (comme le stockage, les véhicules, etc.) par n'importe qui.
</Warning>
