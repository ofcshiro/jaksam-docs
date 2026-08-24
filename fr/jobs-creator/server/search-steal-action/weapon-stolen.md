---
title: "Weapon Stolen"
description: "Se déclenche après qu'un joueur vole quelque chose depuis le menu d'actions, uniquement si tu utilises la fouille/vol de joueur par défaut, ça ne fonctionnera pas si tu l'as remplacée"
icon: "gun"
---

Se déclenche après qu'un joueur vole une arme depuis le menu d'actions.

<Note>
  Ceci ne fonctionne que si tu utilises l'action fouille/vol de joueur par défaut — ça ne se déclenchera pas si tu l'as remplacée par un module personnalisé.
</Note>

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:weaponStolen", function(playerId, targetId, weaponName)
end)
```

```lua Example
-- Cet exemple pour ESX va "supprimer" les armes volées (peut être utile pour les policiers)
RegisterNetEvent("jobs_creator:actions:weaponStolen", function(playerId, targetId, weaponName)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    xPlayer.removeWeapon(weaponName)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Le server ID du joueur qui a volé l'arme |
| `targetId` | integer | Le server ID de la victime qui a perdu l'arme |
| `weaponName` | string | Nom de l'arme |
