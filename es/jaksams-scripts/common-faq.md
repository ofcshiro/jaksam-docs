---
title: "Preguntas frecuentes"
description: "Preguntas frecuentes comunes a todos los scripts"
icon: "circle-user-circle-question"
---

Esta página contiene preguntas frecuentes comunes a todos los scripts. Si tu problema no aparece aquí, revisa la FAQ del script con el que tienes problemas.

<AccordionGroup>
  <Accordion title="Cierre inesperado (crash)">
    Los cierres inesperados pueden tener 2 causas:

    - Debes poner en la whitelist de tu anticheat estos modelos de objeto: `L1_1`, `GetHashKey('L1_1')`, `2116969379`
    - Si sigues teniendo cierres inesperados después de poner estos modelos en la whitelist de tu anticheat, consulta [esta página](/es/jaksams-scripts/troubleshooting)

    _Si no sabes cómo poner modelos de objeto en la whitelist de tu anticheat, pregunta al creador de tu anticheat._
  </Accordion>

  <Accordion title="Attempted to index a nil value (field 'ESX')">
    Si tienes este error, significa que el script no pudo obtener el shared object de ESX.

    Este error puede estar causado por otros errores en tu consola de servidor/F8 que ocurren antes que este.

    Si no tienes ningún otro error antes de ese, consulta [esta página](/es/jaksams-scripts/troubleshooting).
  </Accordion>

  <Accordion title='Cómo solucionar el error "missing menu_default"'>
    Para solucionar el error, simplemente lee el tutorial de instalación del script.
  </Accordion>

  <Accordion title="Los objetos/props no aparecen">
    Si los props no aparecen, lo más probable es que sea un problema de tu anticheat.

    Asegúrate de poner todos los props en la whitelist de tu anticheat. Si no sabes cómo, pregunta al creador de tu anticheat.
  </Accordion>

  <Accordion title="No puedo recibir NINGÚN item">
    Si ya lo has probado con distintos items y no puedes recibir ninguno, revisa [esta página](/es/jaksams-scripts/troubleshooting).
  </Accordion>

  <Accordion title="No puedo recibir SOLO ARMAS">
    Si solo las armas dan problemas pero los items funcionan bien, estas son las posibles razones:

    - En ESX, lo más probable es que tu servidor no soporte el método estándar de ESX `xPlayer.addWeapon`
    - En QBCore, puede que tu inventario esté cambiando el comportamiento por defecto de `qb-inventory`

    Esto no es un problema que dependa del script, sino de tu framework/inventario, y no podemos solucionarlo nosotros: los métodos estándar deben funcionar.
  </Accordion>

  <Accordion title="Cómo reemplazar las notificaciones por defecto">
    Para reemplazar las notificaciones de cualquier script, consulta la documentación del script. Tiene events que permiten desactivar la notificación por defecto y llamar a una externa.

    _Nota: la integración de scripts externos depende completamente de ti._
  </Accordion>

  <Accordion title="Cómo reemplazar la barra de progreso por defecto">
    Para reemplazar la barra de progreso de cualquier script, consulta la documentación del script. Tiene events que permiten desactivar la barra por defecto y llamar a una externa.

    _Nota: la integración de scripts externos depende completamente de ti._
  </Accordion>

  <Accordion title="Transferencias de scripts">
    Los scripts solo se pueden transferir una vez a través del FiveM Keymaster, usando el botón lateral en lugar de "Download". No hay revocaciones ni transferencias manuales en ningún caso.
  </Accordion>

  <Accordion title="Reembolsos">
    Las compras en la tienda de jaksam son definitivas, esto aplica a cualquier situación: framework equivocado, cuentas equivocadas, etc. Por eso, lamentablemente, no podemos ayudar con reembolsos bajo ninguna circunstancia.
  </Accordion>
</AccordionGroup>
