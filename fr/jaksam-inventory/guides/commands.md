---
title: "Commandes"
icon: "slash-forward"
description: "Liste complète des commandes admin pour gérer les items, inventaires et planques"
---

# Commandes Admin

<Note>
  Toutes les commandes admin nécessitent une **permission ACE**. Utilise `/inventory` pour vérifier si tu l'as.
</Note>

## `/inventory`

Ouvre le menu admin pour gérer les items, boutiques, planques, voir les statistiques, etc.

## `/giveitem`

Donne des items à un joueur ou un inventaire.

<ParamField path="inventoryId|playerId|'me'" type="string" required>
  Inventaire cible, ID de joueur, ou `me` pour toi-même
</ParamField>

<ParamField path="itemName" type="string" required>
  Nom de l'item à donner
</ParamField>

<ParamField path="amount" type="number" required>
  Quantité à donner
</ParamField>

<ParamField path="slotId" type="number">
  Slot spécifique optionnel où placer l'item
</ParamField>

```bash
/giveitem me bread 10                     # Donne 10 bread à toi-même
/giveitem 1 water 5                       # Donne 5 water au joueur 1
/giveitem stash_police weapon_pistol 1 3  # Donne 1 weapon_pistol à stash_police dans le slot 3
```

## `/removeitem`

Retire des items d'un joueur ou d'un inventaire.

<ParamField path="inventoryId" type="string" required>
  Inventaire cible ou ID de joueur
</ParamField>

<ParamField path="itemName" type="string" required>
  Nom de l'item à retirer
</ParamField>

<ParamField path="amount" type="number" required>
  Quantité à retirer
</ParamField>

<ParamField path="slotId" type="number">
  Slot spécifique optionnel où retirer l'item
</ParamField>

```bash
/removeitem 1 bread 10                    # Retire 10 bread de l'inventaire du joueur 1
/removeitem stash_police weapon_pistol 1  # Retire 1 weapon_pistol de stash_police
```

## `/clearinventory`

Vide tous les items d'un inventaire. Si `inventoryId` est vide, vide ton propre inventaire. Tu peux aussi exclure un item du vidage.

<ParamField path="inventoryId" type="string">
  Inventaire cible. Utilise ton propre inventaire par défaut si omis
</ParamField>

<ParamField path="excludedItemName" type="string">
  Item à conserver, exclu du vidage
</ParamField>

```bash
/clearinventory          # Vide ton inventaire
/clearinventory 1        # Vide l'inventaire du joueur 1
/clearinventory 2 phone  # Vide l'inventaire du joueur 2 mais garde le phone
```

## `/openinventory`

Ouvre l'inventaire d'un autre joueur.

<ParamField path="targetPlayerId" type="number" required>
  ID du joueur dont ouvrir l'inventaire
</ParamField>

```bash
/openinventory 1  # Ouvre l'inventaire du joueur 1
```

## `/saveinventories`

Force la sauvegarde de tous les inventaires modifiés dans la base de données.

<CardGroup cols={2}>
  <Card title="Gestion de l'inventaire" icon="box-open">
    `/inventory`, `/giveitem`, `/removeitem`, `/clearinventory`
  </Card>

  <Card title="Actions joueur" icon="user">
    `/openinventory`, `/saveinventories`
  </Card>
</CardGroup>
