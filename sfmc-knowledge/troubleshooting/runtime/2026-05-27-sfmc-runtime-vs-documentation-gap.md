---
type: reference
title: Documentation gap versus observed runtime behavior in SFMC
date: 2026-05-27
source: accumulated project observations and general practice
status: reviewed
evidence: observed-runtime
tags: [sfmc, runtime, troubleshooting, documentation-gap, edge-cases]
---

# Resumen

En SFMC hay un patrón recurrente, la documentación o ejemplos públicos no siempre reflejan el comportamiento real en runtime.

# Zonas donde aparece más

- AMPscript temporalidad y contexto de ejecución
- ClaimRow y operaciones pseudo-transaccionales
- SQL con compatibilidades parciales o comportamientos particulares
- SSJS con observabilidad limitada y errores poco descriptivos
- journeys afectados por calidad de dato y reentry más que por la lógica visible

# Implicación práctica

La base de conocimiento debe conservar siempre dos capas:
- fuente declarada
- comportamiento observado

# Recomendación

No tratar la documentación como verdad absoluta cuando el runtime diga otra cosa. Documentar ambos lados con contexto.
