---
type: pattern
title: Hardening estándar para integraciones SSJS con APIs externas
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, api-integration, oauth, logging, hardening, resilience]
status: canonical
---

# Problema

Las integraciones SSJS con APIs externas fallan con facilidad cuando no hay validación de datos, construcción segura de payloads, logging adecuado y separación clara de errores.

# Patrón propuesto

Aplicar un hardening estándar con estos pilares:
- validación previa de registros clave
- payload construido con arrays y `join()`
- autenticación y llamada API en bloques separados
- logging granular por escenario
- `try/catch` por operación crítica
- tratamiento diferenciado de respuestas aceptadas y rechazadas

# Cuándo usarlo

- Integraciones SSJS con OAuth y APIs REST
- Procesos batch en Automation Studio
- Flujos donde algunos registros inválidos no deben bloquear la ejecución global

# Cuándo no usarlo

- Integraciones que requieran transaccionalidad total y rollback completo
- Casos donde SSJS no sea la mejor capa de integración

# Ejemplo

Ver `integrations/azure/2026-05-27-sms-optout-na-architecture.md`.
