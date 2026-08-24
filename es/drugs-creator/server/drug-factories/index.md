---
title: "Drug Factories"
description: "Interiores comprables donde los jugadores pueden producir drogas mediante un proceso de producción de varios pasos."
icon: "industry"
---

Las Drug Factories son interiores comprables donde los jugadores pueden producir drogas mediante un proceso de producción de varios pasos.

## Funciones

- **Compra**: los jugadores pueden comprar una factory a través del menú ingame. Cada factory tiene un precio configurado y un límite de propiedad opcional por jugador
- **Interior**: cada factory usa un IPL (por ejemplo, laboratorio de meth, laboratorio de coca)
- **Estaciones de producción**: las factories tienen estaciones donde los jugadores realizan los pasos de producción (mezclar, prensar, verter). Cada paso consume items de entrada y produce items de salida tras una duración configurada
- **Trabajadores NPC**: los trabajadores de las estaciones pueden contratarse como mejora, aumentando la velocidad de producción mediante multiplicadores configurables. Cada estación admite varios niveles de mejora con costes individuales
- **Stash**: cada factory tiene un stash privado para almacenar ingredientes y productos terminados
- **Whitelist**: los propietarios de la factory pueden poner en whitelist a otros jugadores para darles acceso
- **Visitantes / Timbre**: los jugadores que no están en whitelist pueden tocar el timbre en la entrada de la factory, y el propietario puede permitir o denegar la entrada
- **Venta**: los propietarios pueden vender de nuevo su factory

## Configuración

Toda la configuración de las factories (precios, estaciones, pasos de producción, mejoras, límites de stash) se gestiona a través del menú ingame `/drugscreator`.
