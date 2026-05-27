---
type: playbook
title: Troubleshooting de integraciones API en SFMC con SSJS
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, api-integration, troubleshooting, azure]
status: draft
---

# Objetivo

Diagnosticar fallos en integraciones SSJS con APIs externas, especialmente en autenticación, payload, logging y respuesta de negocio.

# Prerrequisitos

- Script SSJS accesible
- DE de origen y DE de logs accesibles
- Conocimiento de endpoints, autenticación y contrato esperado

# Pasos

1. Validar datos críticos antes de construir el payload
2. Revisar si hay claves vacías como `CUSTOMER_ID`
3. Separar autenticación, construcción de payload, llamada API y logging en bloques distintos
4. Capturar `statusCode` y body de respuestas no exitosas
5. Revisar tratamiento de listas `accepted` y `rejected`
6. Comprobar si el proceso puede reprocesar registros parcialmente fallidos
7. Revisar si el volumen requiere retry, paginación o control de concurrencia

# Validación

- El script no rompe por registros inválidos aislados
- Existe trazabilidad suficiente del error exacto
- Se puede distinguir entre fallo de auth, payload, API o logging

# Errores frecuentes

- JSON montado por concatenación insegura
- Ausencia de validación de campos críticos
- Secretos hardcodeados sin control
- Logging insuficiente para producción
