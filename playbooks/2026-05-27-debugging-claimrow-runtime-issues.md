---
type: playbook
title: Debugging de problemas runtime con ClaimRow
date: 2026-05-27
source: chatgpt-project-mc-arquitecto
tags: [sfmc, amscript, claimrow, troubleshooting, runtime-issues]
status: draft
---

# Objetivo

Diagnosticar duplicados, problemas de tiempo y diferencias de comportamiento de `ClaimRow()` en runtime.

# Prerrequisitos

- DE de cupones accesible
- Datos de prueba controlados
- Posibilidad de hacer envíos reales de test

# Pasos

1. Verificar si el bloque AMPscript se renderiza más de una vez
2. Revisar si hay Content Blocks reutilizados o loops ocultos
3. Comparar comportamiento entre preview, test send y envío real
4. Validar si `ClaimRow()` devuelve `DataRow` o `RowSet` en el patrón usado
5. Confirmar formato y persistencia de `CLAIMED_DATE`
6. Probar fallback cuando no haya stock

# Validación

- Un cupón por customer
- Sin duplicados
- Fecha coherente con el envío real
- Fallback correcto cuando no hay stock

# Errores frecuentes

- Uso de `UpdateDE()` tras `ClaimRow()`
- Uso de `RowCount()` sobre un retorno que no es `RowSet`
- Confiar en `Now()` en contextos de preview como si fuera tiempo real
