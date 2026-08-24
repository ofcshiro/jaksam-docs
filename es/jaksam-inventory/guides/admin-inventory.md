---
title: "Inventario de Admin (Omnipack)"
description: "Accede y gestiona el omnipack de admin, y configura permisos exclusivos para el omnipack"
icon: "warehouse"
---

Si ya tienes permisos de admin (puedes comprobarlo escribiendo `/inventory` dentro del juego), puedes abrir el omnipack simplemente abriendo tu inventario (F2) y luego presionando F1.

<Warning>
  Mover un ítem **AL** omnipack lo **eliminará**.
</Warning>

<Frame>
  ![Captura de pantalla del omnipack](/images/omnipack-screenshot.png)
</Frame>

## Acceso exclusivo al omnipack

Si quieres dar acceso **únicamente** al omnipack sin otorgar acceso al menú de admin y a los comandos, usa el permiso específico:

```bash
add_ace identifier.license:26240584e4v4ca31b22d247b8be6921a8d22j6m1 jaksam_inventory.omnipack allow # Otorga únicamente el permiso del omnipack
```

Con este permiso, el jugador podrá:

<CardGroup cols={2}>
  <Card title="Puede hacer" icon="check">
    Usar el omnipack (F1 en el inventario)
  </Card>

  <Card title="No puede hacer" icon="xmark">
    Abrir el menú de admin (`/inventory`)

    Usar comandos de admin (`/giveitem`, `/removeitem`, etc.)
  </Card>
</CardGroup>
