---
type: decision
title: Arquitectura batch resiliente para flujo de opt-out SMS con Azure
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, azure, batch-processing, optout, architecture, resilience]
status: canonical
---

# Decisión

Adoptar una arquitectura batch resiliente que tolere registros inválidos y mantenga continuidad de ejecución con logging exhaustivo.

# Contexto

El script SSJS original fallaba por registros con `CUSTOMER_ID` vacío, payload JSON inseguro y baja visibilidad operativa. Parar todo el batch por unos pocos registros defectuosos aumentaba el riesgo operacional.

# Motivo

- Evitar bloqueos globales por errores parciales
- Mejorar trazabilidad del fallo exacto
- Facilitar troubleshooting en producción
- Mantener operatividad del proceso transaccional

# Consecuencias

- Algunos registros se omiten y quedan trazados por log
- Aumenta el volumen de logging
- La robustez operativa prima sobre la simplicidad del script
- Sigue pendiente una estrategia formal de reprocesamiento

# Alternativas consideradas

- Fallar todo el batch ante cualquier dato inválido
- Mantener JSON construido por concatenación manual
- Reducir logging para simplificar el script
