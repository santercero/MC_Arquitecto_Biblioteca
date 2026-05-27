---
type: reference
title: SSJS integration pitfalls first cut
date: 2026-05-27
source: project library plus general practice
status: reviewed
evidence: observed-runtime
tags: [sfmc, ssjs, api-integration, pitfalls, troubleshooting]
---

# Pitfalls frecuentes

- secrets hardcodeados
- JSON construido manualmente dentro de loops
- logging insuficiente
- errores no diferenciados por bloque
- ausencia de retry, reprocesamiento o control de concurrencia

# Buenas prácticas mínimas

- validar entrada antes de construir payload
- separar auth, payload, HTTP y logs
- capturar errores de negocio y de logging
- pensar en resiliencia parcial

# Relación

- `patterns/2026-05-27-pattern-ssjs-api-integration-hardening.md`
- `patterns/2026-05-27-pattern-safe-json-construction-in-ssjs.md`
