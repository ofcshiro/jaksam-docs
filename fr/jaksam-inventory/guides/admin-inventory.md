---
title: "Inventaire Admin (Omnipack)"
description: "Accède et gère l'omnipack admin, et configure des permissions réservées à l'omnipack"
icon: "warehouse"
---

Si tu as déjà les permissions admin (tu peux le vérifier en tapant `/inventory` en jeu), tu peux ouvrir l'omnipack en ouvrant simplement ton inventaire (F2), puis en appuyant sur F1.

<Warning>
  Déplacer un item **VERS** l'omnipack le **supprimera**.
</Warning>

<Frame>
  ![Omnipack screenshot](/images/omnipack-screenshot.png)
</Frame>

## Accès uniquement à l'omnipack

Si tu veux donner l'accès **uniquement** à l'omnipack sans donner accès au menu admin et aux commandes, utilise la permission spécifique :

```bash
add_ace identifier.license:26240584e4v4ca31b22d247b8be6921a8d22j6m1 jaksam_inventory.omnipack allow # N'autorise que la permission omnipack
```

Avec cette permission, le joueur pourra :

<CardGroup cols={2}>
  <Card title="Peut faire" icon="check">
    Utiliser l'omnipack (F1 dans l'inventaire)
  </Card>

  <Card title="Ne peut pas faire" icon="xmark">
    Ouvrir le menu admin (`/inventory`)

    Utiliser les commandes admin (`/giveitem`, `/removeitem`, etc.)
  </Card>
</CardGroup>
