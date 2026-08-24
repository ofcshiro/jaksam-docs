---
title: "Hired Dealers"
description: "Dealers NPC que los jugadores contratan para vender drogas de forma pasiva en territorios que poseen."
icon: "user-tie"
---

Los Hired Dealers son dealers NPC que los jugadores pueden contratar a través del **Trap Phone** para vender drogas de forma pasiva en territorios que poseen.

Los jugadores deben poseer un [territorio](/es/drugs-creator/server/territories) para contratar un dealer en él. Cada dealer puede abastecerse con drogas, y las venderá de forma autónoma con el tiempo, acumulando ganancias que el jugador puede recoger.

El sistema incluye una mecánica de **heat**: cada venta aumenta el heat del dealer, lo que incrementa la probabilidad de que el dealer sea arrestado o robado. El heat va bajando con el tiempo.

## Trap Phone

El Trap Phone es un item de inventario usable (`trap_phone`) que abre la UI de gestión. Desde ahí, los jugadores pueden:

- Contratar y despedir dealers en territorios propios
- Abastecer a los dealers con drogas
- Recoger las ganancias
- Ver las notificaciones del dealer (ventas, arrestos, robos, pérdida de territorio, sin stock)
- Solicitar encuentros para interactuar con un dealer ingame
- Ver la información del territorio
- Activar/desactivar la venta en la esquina (si está habilitada)

El item debe registrarse en la lista de items de tu framework — consulta la página de [Instalación](/es/drugs-creator/installation) para ver la definición del item.

## Configuración

Toda la configuración de los hired dealers (precios, intervalos de venta, dealers máximos, sistema de heat, drogas aceptadas) se gestiona a través del menú ingame `/drugscreator`.
