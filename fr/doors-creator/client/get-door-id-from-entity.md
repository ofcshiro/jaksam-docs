---
title: "Get door ID from entity"
description: "Résout l'ID d'une porte à partir de son entity handle."
icon: "magnifying-glass"
---

```lua Export
exports["doors_creator"]:getDoorIdFromEntity(entity)
```

### Paramètres

| Nom     | Type de donnée | Description                                  |
| -------- | --------- | ----------------------------------------------- |
| `entity` | integer   | L'entity handle dont récupérer l'ID de porte        |

### Valeur de retour

| Type de donnée | Description                            |
| --------- | ----------------------------------------- |
| integer   | L'ID de la porte si trouvé, `nil` sinon      |

## Exemple

```lua
-- Cet exemple montre comment ajouter une option de cible pour vérifier les IDs de porte avec ox_target
-- Remarque : ceci n'est qu'un exemple, tu devras l'adapter à tes besoins et à ton système de cible
Citizen.CreateThread(function()
    exports.ox_target:addGlobalObject({
        {
            name = 'check_door_id',
            icon = 'fas fa-door-open',
            label = 'Check Door ID',
            onSelect = function(data)
                local doorId = exports["doors_creator"]:getDoorIdFromEntity(data.entity)

                if doorId then
                    print("Found door with ID: " .. doorId)
                end
            end
        }
    })
end)
```
