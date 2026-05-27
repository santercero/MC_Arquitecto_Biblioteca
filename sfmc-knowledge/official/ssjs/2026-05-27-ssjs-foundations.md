---
type: reference
title: SSJS foundations
date: 2026-05-27
source: general SFMC practice and observed behavior
status: reviewed
evidence: community-confirmed
tags: [sfmc, ssjs, automation-studio, scripting, api-integration]
---

# Resumen

SSJS permite ejecutar lógica server-side en Automation Studio, CloudPages y otros contextos específicos de SFMC. Es útil para integraciones, tratamiento de datos y automatización más flexible que AMPscript.

# Capacidades clave

- llamadas HTTP
- manipulación de objetos y JSON
- acceso a Data Extensions
- control de flujo más expresivo
- integración con APIs externas

# Límites y riesgos

- el manejo de errores es sensible y a menudo pobre si no se diseña bien
- secrets hardcodeados son un riesgo frecuente
- payloads construidos manualmente pueden romperse con facilidad
- la observabilidad suele ser limitada si no se diseña logging explícito

# Buenas prácticas

- validar datos críticos antes de procesar
- separar auth, payload, ejecución y logging
- registrar tanto errores funcionales como fallos de logging
- pensar en reprocesamiento y resiliencia parcial

# Relación con otros documentos

- `patterns/2026-05-27-pattern-ssjs-api-integration-hardening.md`
- `patterns/2026-05-27-pattern-safe-json-construction-in-ssjs.md`
- `playbooks/2026-05-27-sfmc-api-integration-debugging.md`
