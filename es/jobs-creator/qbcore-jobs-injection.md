---
title: "Inyección de jobs en QBCore"
description: "Soluciona el problema de otros scripts que no reconocen los jobs de Jobs Creator en QBCore debido al orden de inicio de los scripts."
icon: "plug"
---

Normalmente no es necesario añadir ningún código. Aun así, un orden de inicio de scripts diferente puede provocar que otros scripts no reconozcan los jobs de Jobs Creator en QBCore.

## ¿Cómo puedo solucionar esto?

La solución es muy sencilla: añade el siguiente event tanto en el cliente como en el servidor en el script que no reconoce los jobs de Jobs Creator:

```lua
-- Integración de jaksam's Jobs Creator
AddEventHandler('jobs_creator:injectJobs', function(jobs)
    -- Asigna los nuevos jobs al objeto de QBCore, la siguiente línea depende de cómo esté estructurado tu script
    QBCore.Shared.Jobs = jobs
end)
```
