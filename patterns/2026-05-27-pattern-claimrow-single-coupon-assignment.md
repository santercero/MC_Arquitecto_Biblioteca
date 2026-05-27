---
type: pattern
title: Patrón ClaimRow para asignación única de cupones
date: 2026-05-27
source: chatgpt-project-mc-arquitecto
tags: [sfmc, amscript, claimrow, coupons, transactional-logic, data-extensions]
status: canonical
---

# Problema

Asignar un recurso único, como un cupón, por cliente y por envío evitando duplicados y registrando el claim.

# Patrón propuesto

Resolver la selección, bloqueo y actualización del claim dentro de una única llamada a `ClaimRow()`, incluyendo en esa llamada los campos de tracking necesarios, como `CUSTOMER_ID` y `CLAIMED_DATE`.

# Cuándo usarlo

- Asignación de cupones únicos
- Pools limitados de recursos
- Tracking simple del consumo del recurso
- Escenarios donde la atomicidad sea prioritaria

# Cuándo no usarlo

- Cuando el proceso requiere múltiples escrituras relacionadas con consistencia fuerte fuera de la DE del claim
- Cuando se necesita una auditoría compleja separada en tiempo real

# Ejemplo

Ver `snippets/2026-05-27-ampscript-claimrow-coupon-assignment.md`.
