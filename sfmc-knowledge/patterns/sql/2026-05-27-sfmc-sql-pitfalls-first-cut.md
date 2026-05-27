---
type: reference
title: SFMC SQL pitfalls first cut
date: 2026-05-27
source: project library plus general practice
status: reviewed
evidence: observed-runtime
tags: [sfmc, sql, pitfalls, query-activity, troubleshooting]
---

# Pitfalls frecuentes

- asumir compatibilidad total con SQL Server
- no controlar multiplicidad en joins
- deduplicar sin criterio explícito
- usar aliases conflictivos sin escape
- subestimar coste de subqueries correlacionadas
- no documentar claves de unicidad esperadas

# Buenas prácticas mínimas

- reducir dataset pronto
- validar cardinalidad
- explicitar criterio de latest record
- separar query productiva de query de diagnóstico

# Relación

- `patterns/2026-05-27-pattern-sfmc-service-cloud-aliases.md`
