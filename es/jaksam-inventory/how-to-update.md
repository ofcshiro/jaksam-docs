---
title: "Cómo"
icon: "rectangle-new"
tag: "Update"
description: "Mantén tu instalación de Jaksam Inventory actualizada sin perder tus ítems personalizados, ajustes, integraciones u otras personalizaciones."
---

# Actualizar Jaksam Inventory

<Warning>
  **Crea siempre una copia de seguridad antes de actualizar.** Nunca elimines tu instalación existente antes de tener una copia de seguridad funcional.
</Warning>

## Antes de Empezar

<Tip>
  **Recomendado:** Conserva tu copia de seguridad durante al menos unos días después de la actualización. Esto facilita revertir los cambios si algo sale mal.
</Tip>

<CardGroup cols={2}>
  <Card title="Detén tu Servidor" icon="server">
    Detén siempre tu servidor de FiveM antes de reemplazar los archivos del inventario.
  </Card>

  <Card title="Crea una Copia de Seguridad" icon="floppy-disk">
    Haz una copia de seguridad de tus archivos y carpetas personalizados antes de instalar la nueva versión.
  </Card>

  <Card title="Instala la Actualización" icon="download">
    Elimina la versión anterior y sube la última versión de Jaksam Inventory.
  </Card>

  <Card title="Restaura las Personalizaciones" icon="rotate">
    Restaura tus archivos respaldados en la nueva instalación.
  </Card>
</CardGroup>

## ¿Qué Debo Respaldar?

### Siempre Respaldar

Estos archivos y carpetas **siempre** deben incluirse en tu copia de seguridad:

| Archivo / Carpeta | Descripción |
| --- | --- |
| `_data/` | Ítems y ajustes del inventario |
| `_backups/` | Copias de seguridad de la lista de ítems |
| `_hooks/` | Recetas de crafting y lógica personalizada |
| `_modules/` | Integraciones con scripts externos |
| `integrations/` | Ajustes de integración |
| `current_config.json` | Archivo de configuración principal |

### Archivos Personalizados

Respalda estos únicamente si los has modificado o agregado:

| Archivo / Carpeta | Descripción |
| --- | --- |
| `_images/` | Imágenes personalizadas de ítems |
| `dist/assets/variables.css` | Colores personalizados del tema |
| `_locales/` | Traducciones personalizadas |
| `dist/menu_translations/` | Traducciones personalizadas del menú |

<Note>
  Si no has personalizado ninguno de los archivos mencionados arriba, no necesitas respaldarlos.
</Note>

## Proceso de Actualización

Sigue estos pasos **en orden**.

## Referencia Rápida

| Archivo / Carpeta | Copia de Seguridad Requerida | Propósito |
| --- | :-: | --- |
| `_data/` | Sí | Ítems y ajustes |
| `_backups/` | Sí | Copias de seguridad de la lista de ítems |
| `_hooks/` | Sí | Crafting y lógica personalizada |
| `_modules/` | Sí | Integraciones externas |
| `integrations/` | Sí | Ajustes de integración |
| `current_config.json` | Sí | Configuración principal |
| `_images/` | Personalizado | Imágenes personalizadas de ítems |
| `dist/assets/variables.css` | Personalizado | Personalización del tema |
| `_locales/` | Personalizado | Traducciones personalizadas |
| `dist/menu_translations/` | Personalizado | Traducciones del menú |

## Solución de Problemas

<AccordionGroup>
  <Accordion title="Mis ítems desaparecieron">
    Restaura la carpeta `_data/` desde tu copia de seguridad y reinicia el servidor.
  </Accordion>

  <Accordion title="Faltan mis recetas de crafting">
    Restaura la carpeta `_hooks/` desde tu copia de seguridad.
  </Accordion>

  <Accordion title="Mis ajustes se reiniciaron">
    Restaura `current_config.json` desde tu copia de seguridad.
  </Accordion>

  <Accordion title="Los colores de mi tema se reiniciaron">
    Restaura `dist/assets/variables.css` desde tu copia de seguridad si personalizaste el tema predeterminado.
  </Accordion>

  <Accordion title="Faltan mis imágenes personalizadas">
    Restaura tu carpeta `_images/` personalizada.
  </Accordion>

  <Accordion title="Faltan mis traducciones">
    Restaura `_locales/` y/o `dist/menu_translations/`, según qué archivos de traducción hayas personalizado.
  </Accordion>

  <Accordion title="Mi servidor no inicia">
    1. Asegúrate de que la nueva carpeta `jaksam_inventory` esté instalada correctamente.
    2. Asegúrate de que tus archivos de copia de seguridad se hayan restaurado en las ubicaciones correctas.
    3. Espera aproximadamente 30 segundos después de iniciar el servidor, ya que la base de datos puede estar actualizándose automáticamente.
    4. Revisa la consola de tu servidor en busca de errores.
    5. Si el problema persiste, restaura tu copia de seguridad anterior y contacta con soporte.
  </Accordion>
</AccordionGroup>

## Importante

<Warning>
  **Nunca elimines tu copia de seguridad inmediatamente después de una actualización exitosa.** Consérvala durante unos días por si descubres algún problema más adelante.
</Warning>

<Check>
  Una vez que todo funcione correctamente, tu actualización de Jaksam Inventory estará completa.
</Check>
