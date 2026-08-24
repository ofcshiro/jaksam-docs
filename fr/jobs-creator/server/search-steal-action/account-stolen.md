---
title: "Account stolen"
description: "Se déclenche après qu'un joueur vole de l'argent via le menu d'actions, uniquement lors de l'utilisation de l'action fouille/vol par défaut."
icon: "money-bill-transfer"
---

Se déclenche après qu'un joueur vole de l'argent depuis le menu d'actions.

<Note>
  Ceci ne fonctionne que si tu utilises l'action fouille/vol de joueur par défaut — ça ne se déclenchera pas si tu l'as remplacée par un module personnalisé.
</Note>

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:accountStolen", function(playerId, targetId, accountName, amount)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:actions:accountStolen", function(playerId, targetId, accountName, amount)
    print(GetPlayerName(playerId) .. " has stolen " .. amount .. " " .. accountName .. " from " .. GetPlayerName(targetId))
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Le server ID du joueur qui a volé l'argent |
| `targetId` | integer | Le server ID de la victime qui a perdu l'argent |
| `accountName` | string | Nom du compte (exemple : "bank") |
| `amount` | integer | Montant volé |
