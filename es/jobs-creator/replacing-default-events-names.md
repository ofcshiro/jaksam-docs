---
title: "Reemplazar los nombres de events por defecto"
description: "Renombra los nombres de events externos que dispara Jobs Creator para que coincidan con los scripts de tu propio servidor."
icon: "pen"
hidden: true
---

# Reemplazar los nombres de events por defecto

En caso de que tu servidor use nombres de events distintos a los predeterminados, puedes editar esos nombres en `jobs_creator/integrations/cl_integrations.lua` **y** `jobs_creator/integrations/sv_integrations.lua`

Ejemplo de los nombres por defecto:

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

<br />Ejemplo de nombres editados:

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
