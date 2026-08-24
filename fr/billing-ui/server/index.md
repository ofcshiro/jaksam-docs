---
title: "Serveur"
description: "Events et exports du côté serveur disponibles dans Billing UI."
icon: "server"
---

Cette page liste les events et exports du **côté serveur** disponibles dans Billing UI.

<CardGroup cols={2}>
  <Card title="Créer une facture" icon="file-circle-plus" href="/fr/billing-ui/server/create-bill">
    Crée une nouvelle facture pour un joueur ou une société.
  </Card>

  <Card title="Supprimer une facture" icon="trash" href="/fr/billing-ui/server/delete-bill">
    Supprime une facture via son ID.
  </Card>

  <Card title="Rafraîchir une facture" icon="rotate" href="/fr/billing-ui/server/refresh-bill">
    Rafraîchit une facture après l'avoir modifiée directement en base de données.
  </Card>

  <Card title="Facture créée" icon="file-invoice" href="/fr/billing-ui/server/on-bill-created">
    Se déclenche quand une facture est créée.
  </Card>

  <Card title="Facture payée" icon="circle-check" href="/fr/billing-ui/server/on-bill-paid">
    Se déclenche quand une facture est payée.
  </Card>
</CardGroup>
