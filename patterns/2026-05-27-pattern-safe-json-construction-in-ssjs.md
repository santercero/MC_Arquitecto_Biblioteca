---
type: pattern
title: Construcción segura de payload JSON en SSJS usando arrays y join
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, json, payload-validation, hardening]
status: canonical
---

# Problema

La concatenación manual de JSON dentro de loops puede generar payloads inválidos, separadores erróneos y errores difíciles de diagnosticar.

# Patrón propuesto

Construir cada fragmento o elemento en una estructura controlada, acumularlo en un array y generar el bloque final con `join(',')`.

# Cuándo usarlo

- Payloads batch con múltiples registros
- Integraciones donde algunos registros pueden omitirse
- Scripts SSJS con construcción dinámica de JSON

# Cuándo no usarlo

- Payloads triviales de un único objeto fijo
- Escenarios donde una librería segura de serialización esté disponible y sea preferible

# Ejemplo

Ver `snippets/2026-05-27-ssjs-safe-json-array-builder.md`.
