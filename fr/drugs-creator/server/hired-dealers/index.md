---
title: "Hired Dealers"
description: "Dealers PNJ que les joueurs engagent pour vendre passivement des drogues dans les territoires qu'ils possèdent."
icon: "user-tie"
---

Les Hired Dealers sont des dealers PNJ que les joueurs peuvent engager via le **Trap Phone** pour vendre passivement des drogues dans les territoires qu'ils possèdent.

Les joueurs doivent posséder un [territoire](/fr/drugs-creator/server/territories) pour y engager un dealer. Chaque dealer peut être approvisionné en drogues, et les vendra de manière autonome au fil du temps, accumulant des gains que le joueur peut récupérer.

Le système inclut une mécanique de **heat** (chaleur) : chaque vente augmente la heat du dealer, ce qui accroît le risque qu'il se fasse arrêter ou braquer. La heat diminue avec le temps.

## Trap Phone

Le Trap Phone est un item d'inventaire utilisable (`trap_phone`) qui ouvre l'UI de gestion. Depuis celle-ci, les joueurs peuvent :

- Engager et licencier des dealers dans les territoires possédés
- Approvisionner les dealers en drogues
- Récupérer les gains
- Consulter les notifications des dealers (ventes, arrestations, braquages, perte de territoire, rupture de stock)
- Demander des rendez-vous pour interagir avec un dealer en jeu
- Consulter les informations du territoire
- Activer/désactiver la vente au coin de la rue (si activée)

L'item doit être enregistré dans la liste d'items de ton framework — voir la page [Installation](/fr/drugs-creator/installation) pour la définition de l'item.

## Configuration

Tous les paramètres des hired dealers (tarification, intervalles de vente, nombre max de dealers, système de heat, drogues acceptées) sont gérés via le menu ingame `/drugscreator`.
