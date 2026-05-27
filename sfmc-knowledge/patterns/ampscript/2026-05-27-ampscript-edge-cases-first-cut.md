---
type: reference
title: AMPscript edge cases first cut
date: 2026-05-27
source: project library plus general practice
status: reviewed
evidence: observed-runtime
tags: [sfmc, amscript, edge-cases, troubleshooting]
---

# Edge cases frecuentes

- diferencias entre preview y envío real
- funciones temporales con evaluación no intuitiva
- retorno ambiguo de ciertas funciones según contexto
- duplicidad aparente por renderizados múltiples
- errores silenciosos por valores vacíos o formato de campo

# Buenas prácticas mínimas

- validar con datos reales
- controlar vacíos y tipos
- aislar bloques críticos durante debugging
- documentar contexto exacto del fallo

# Relación

- `patterns/2026-05-27-pattern-claimrow-single-coupon-assignment.md`
