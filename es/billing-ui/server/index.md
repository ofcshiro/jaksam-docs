---
title: "Server"
description: "Events y exports del lado del servidor disponibles en Billing UI."
icon: "server"
---

Esta página enumera los events y exports del **lado del servidor** disponibles en Billing UI.

<CardGroup cols={2}>
  <Card title="Crear factura" icon="file-circle-plus" href="/es/billing-ui/server/create-bill">
    Crea una nueva factura para un jugador o sociedad.
  </Card>

  <Card title="Eliminar factura" icon="trash" href="/es/billing-ui/server/delete-bill">
    Elimina una factura mediante su ID.
  </Card>

  <Card title="Actualizar factura" icon="rotate" href="/es/billing-ui/server/refresh-bill">
    Actualiza una factura después de editarla directamente en la base de datos.
  </Card>

  <Card title="On bill created" icon="file-invoice" href="/es/billing-ui/server/on-bill-created">
    Se dispara cuando se crea una factura.
  </Card>

  <Card title="On bill paid" icon="circle-check" href="/es/billing-ui/server/on-bill-paid">
    Se dispara cuando se paga una factura.
  </Card>
</CardGroup>
