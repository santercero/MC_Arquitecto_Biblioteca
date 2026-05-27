---
type: decision
title: Usar ClaimRow como operación atómica para asignación de cupones
date: 2026-05-27
source: chatgpt-project-mc-arquitecto
tags: [sfmc, amscript, claimrow, architecture, concurrency]
status: canonical
---

# Decisión

Usar `ClaimRow()` como operación transaccional única para reclamar y actualizar el cupón en una sola llamada.

# Contexto

Durante las pruebas, el uso posterior de `UpdateDE()` provocó errores, ambigüedades de sintaxis y menor fiabilidad. También se observaron posibles duplicados y diferencias entre el comportamiento documentado y el comportamiento real en runtime.

# Motivo

- Menor complejidad operativa
- Menor riesgo de duplicados
- Mejor alineación con el comportamiento real observado
- Evita depender de actualizaciones posteriores menos estables

# Consecuencias

- La lógica de tracking principal debe resolverse dentro de `ClaimRow()`
- Se reduce el uso de operaciones complementarias sobre el mismo registro
- El diseño queda más acoplado a las capacidades y límites de `ClaimRow()`

# Alternativas consideradas

- Reclamar primero y actualizar después con `UpdateDE()`
- Añadir logging separado desde el inicio
- Usar campos Date en vez de Text para `CLAIMED_DATE`
