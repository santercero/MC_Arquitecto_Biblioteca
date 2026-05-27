---
type: chat-summary
title: Refactorización y hardening del script SSJS "SMS Opt Out Azure Transac" para integración Azure API en SFMC NA
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, automation-studio, azure, api-integration, sms, optout, northamerica, error-handling, json, logging, oauth, production, security, hardening, debugging]
status: canonical
---

# Contexto

Se documenta la evolución de un script SSJS productivo en Norteamérica para procesar opt-outs SMS mediante integración API con Azure.

# Pregunta o necesidad

Corregir y endurecer un script SSJS que fallaba de forma intermitente al autenticar, construir payloads JSON y enviar registros de opt-out a una API externa.

# Respuesta útil

La refactorización correcta combina validación estricta de `CUSTOMER_ID`, construcción segura del payload mediante arrays y `join()`, logging granular, trazabilidad con `Write()` y manejo de errores por bloques críticos.

# Decisiones o conclusiones

- Ignorar registros con `CUSTOMER_ID` vacío sin detener el batch completo
- Construir JSON usando arrays y `join(',')`
- Mantener OAuth `client_credentials`
- Centralizar logs en `DE_smsLog`
- Añadir logging incluso para errores de logging
- Priorizar robustez y trazabilidad frente a simplicidad

# Snippets o artefactos mencionados

Ver `snippets/2026-05-27-ssjs-safe-json-array-builder.md`, `snippets/2026-05-27-ssjs-oauth-client-credentials-sfmc.md` y `integrations/azure/2026-05-27-sms-optout-na-architecture.md`.

# Acciones siguientes

- Revisar estrategia de gestión de secretos, hoy todavía hardcodeados
- Definir política de retry y reprocesamiento
- Añadir control de concurrencia o marca de procesado si el volumen crece
