---
title: "Utilisation des commandes"
description: "Commandes console et in-game pour gérer l'allowlist et la priorité de la queue."
icon: "terminal"
---

Toutes les commandes peuvent être utilisées soit in-game par les admins du serveur, soit directement depuis la console du serveur.

### Add allowlist

```
/add_allowlist identifier/requestId
```

Le paramètre peut être soit un identifier **soit** un ID de requête.

| Paramètre    | Type    | Description                                                                                                                        |
| ------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `identifier` | string  | L'identifier **principal** du joueur (peut être le Steam hex, la licence Rockstar, ou l'ID Discord). Utilise l'identifier configuré dans les paramètres du script. |
| `requestId`  | integer | L'ID de la requête. C'est l'ID affiché aux joueurs après qu'ils envoient la demande d'allowlist.                                       |

#### Exemple

```
/add_allowlist 7b1261c1ae07dr156af762fcb1bec11a403b9413
```

### Remove allowlist

```
/remove_allowlist identifier
```

Le paramètre **doit** être l'identifier principal du joueur.

| Paramètre    | Type   | Description                                                                                                                        |
| ------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `identifier` | string | L'identifier **principal** du joueur (peut être le Steam hex, la licence Rockstar, ou l'ID Discord). Utilise l'identifier configuré dans les paramètres du script. |

#### Exemple

```
/remove_allowlist 7b1261c1ae07dr156af762fcb1bec11a403b9413
```

### Set queue priority

```
/set_queue_priority identifier/playerId priority
```

Le **premier** paramètre peut être un identifier principal **ou** un ID de joueur (si le joueur est en ligne).

| Paramètre    | Type    | Description                                                                                                                        |
| ------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `identifier` | string  | L'identifier **principal** du joueur (peut être le Steam hex, la licence Rockstar, ou l'ID Discord). Utilise l'identifier configuré dans les paramètres du script. |
| `playerId`   | integer | Le server ID du joueur.                                                                                                          |
| `priority`   | integer | La priorité du joueur. Nombre plus élevé = plus de priorité.                                                                            |

#### Exemple

```
/set_queue_priority 7b1261c1ae07dr156af762fcb1bec11a403b9413 15
```
