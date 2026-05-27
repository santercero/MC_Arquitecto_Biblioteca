---
type: reference
title: Arquitectura de integración Azure para SMS Opt Out NA
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, azure, sms, optout, northamerica, production, architecture]
status: canonical
file: SSJS - SMS Opt Out Azure Transac
---

# Qué es este documento

Describe la arquitectura funcional y técnica observada para un script SSJS productivo que procesa opt-outs SMS en Norteamérica contra una API Azure.

# Por qué importa

Combina varios elementos críticos, OAuth, payload batch, logging operativo, tolerancia a errores parciales y endpoint de negocio productivo.

# Qué conocimiento extraer

- Patrón de hardening para integraciones SSJS
- Estrategia de resiliencia batch
- Riesgos de secretos hardcodeados
- Necesidad de estrategia futura de retry y reprocesamiento

# Relación con otros artefactos

- `summaries/2026-05-27-sms-optout-azure-hardening-summary.md`
- `patterns/2026-05-27-pattern-ssjs-api-integration-hardening.md`
- `patterns/2026-05-27-pattern-safe-json-construction-in-ssjs.md`
- `playbooks/2026-05-27-sfmc-api-integration-debugging.md`
