---
type: chat-summary
title: ClaimRow en Salesforce Marketing Cloud: asignación segura de cupones únicos, problemas reales y patrón reutilizable
date: 2026-05-27
source: chatgpt-project-mc-arquitecto
tags: [sfmc, amscript, claimrow, coupons, data-extensions, concurrency, runtime-issues, architecture]
status: canonical
---

# Contexto

Se analizó y depuró un proceso de asignación de cupones únicos mediante `ClaimRow()` en AMPscript dentro de Salesforce Marketing Cloud.

# Pregunta o necesidad

Asignar un único cupón por cliente al recibir un email, registrando `CUSTOMER_ID` y `CLAIMED_DATE`, evitando duplicados y con compatibilidad con una Business Unit local.

# Respuesta útil

La forma más estable y segura de usar `ClaimRow()` es realizar toda la actualización necesaria dentro de la propia llamada a `ClaimRow()`, evitando `UpdateDE()`, `InsertDE()` u otras modificaciones posteriores sobre el mismo registro reclamado.

También se observó que `Now()` puede comportarse de forma no dinámica en ciertos contextos de preview, test send o ejecución batch, y que `ClaimRow()` puede devolver tipos distintos según cómo se invoque.

# Decisiones o conclusiones

- Evitar `UpdateDE()` tras `ClaimRow()`
- Tratar `ClaimRow()` como una operación atómica de selección, lock y actualización
- Usar `CLAIMED_DATE` como campo `Text` para reducir errores silenciosos de formato
- Validar el retorno con `Empty()` en lugar de asumir un `RowSet`

# Snippets o artefactos mencionados

Ver `snippets/2026-05-27-ampscript-claimrow-coupon-assignment.md`.

# Acciones siguientes

- Validar el patrón en envíos reales, no solo previews
- Verificar si hay bloques reutilizados o renderizados múltiples cuando aparezcan duplicados
- Documentar referencias oficiales y de comunidad en una nota separada
