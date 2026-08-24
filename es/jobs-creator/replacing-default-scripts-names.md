---
title: "Reemplazar nombres por defecto"
description: "Personaliza los nombres de script, event y export que usa Jobs Creator para que coincidan con la configuración de tu servidor."
icon: "pen-to-square"
---

## Reemplazar los nombres de script por defecto

En caso de que tu servidor use nombres de script distintos a los predeterminados, puedes editar esos nombres directamente en los ajustes del menú dentro del juego. Esto es perfecto cuando renombras un script por cualquier motivo y sus exports no se modifican.

<Note>
  El script que selecciones debe usar el mismo export para que funcione correctamente.
</Note>

## Reemplazar los nombres de event por defecto

En caso de que tu servidor use nombres de event distintos a los predeterminados, puedes editar esos nombres en `jobs_creator/integrations/cl_integrations.lua` **y** `jobs_creator/integrations/sv_integrations.lua`.

**Ejemplo de nombres por defecto:**

```lua
EXTERNAL_EVENTS_NAMES = {
    ["esx:getSharedObject"] = nil,

    ["esx_skin:save"] = "esx_skin:save",
    ["esx_billing:sendBill"] = "esx_billing:sendBill",
    ["jsfour-idcard:open"] = "jsfour-idcard:open",
    ["esx_license:removeLicense"] = "esx_license:removeLicense",
    ["esx_license:addLicense"] = "esx_license:addLicense",
}
```

**Ejemplo de nombres editados:**

```lua
EXTERNAL_EVENTS_NAMES = {
    ["esx:getSharedObject"] = "gamemode:getSharedObject",

    ["esx_skin:save"] = "my_skin_script:save",
    ["esx_billing:sendBill"] = "billing_ui:sendBill",
    ["jsfour-idcard:open"] = "jsfour-idcard:open",
    ["esx_license:removeLicense"] = "licenses:removeLicense",
    ["esx_license:addLicense"] = "licenses:addLicense",
}
```
