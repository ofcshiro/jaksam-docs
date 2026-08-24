---
title: "Uso de comandos"
description: "Comandos de consola e ingame para gestionar la allowlist y la prioridad de la queue."
icon: "terminal"
---

Todos los comandos pueden usarse tanto ingame por administradores del servidor como directamente desde la consola del servidor.

### Add allowlist

```
/add_allowlist identifier/requestId
```

El parámetro puede ser un identifier **o** un request ID.

| Parámetro    | Tipo    | Descripción                                                                                                                        |
| ------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `identifier` | string  | El identifier **principal** del jugador (puede ser el Steam hex, la licencia de Rockstar, o el ID de Discord). Usa el identifier configurado en los ajustes del script. |
| `requestId`  | integer | El ID de la solicitud. Es el ID que se muestra a los jugadores después de enviar la solicitud de allowlist.                                       |

#### Ejemplo

```
/add_allowlist 7b1261c1ae07dr156af762fcb1bec11a403b9413
```

### Remove allowlist

```
/remove_allowlist identifier
```

El parámetro **debe** ser el identifier principal del jugador.

| Parámetro    | Tipo   | Descripción                                                                                                                        |
| ------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `identifier` | string | El identifier **principal** del jugador (puede ser el Steam hex, la licencia de Rockstar, o el ID de Discord). Usa el identifier configurado en los ajustes del script. |

#### Ejemplo

```
/remove_allowlist 7b1261c1ae07dr156af762fcb1bec11a403b9413
```

### Set queue priority

```
/set_queue_priority identifier/playerId priority
```

El **primer** parámetro puede ser un identifier principal **o** un player ID (si el jugador está online).

| Parámetro    | Tipo    | Descripción                                                                                                                        |
| ------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `identifier` | string  | El identifier **principal** del jugador (puede ser el Steam hex, la licencia de Rockstar, o el ID de Discord). Usa el identifier configurado en los ajustes del script. |
| `playerId`   | integer | El ID de servidor del jugador.                                                                                                          |
| `priority`   | integer | La prioridad del jugador. Un número más alto = más prioridad.                                                                            |

#### Ejemplo

```
/set_queue_priority 7b1261c1ae07dr156af762fcb1bec11a403b9413 15
```
