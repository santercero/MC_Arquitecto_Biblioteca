---
type: reference
title: SQL Query Activities foundations
date: 2026-05-27
source: general SFMC practice and observed behavior
status: reviewed
evidence: community-confirmed
tags: [sfmc, sql, query-activity, automation-studio, data-extensions]
---

# Resumen

El SQL de Marketing Cloud se usa principalmente en Query Activities para poblar o transformar Data Extensions. Está muy orientado a segmentación, modelado intermedio y preparación de audiencias.

# Capacidades clave

- joins entre Data Extensions y Data Views
- agregaciones y deduplicación
- normalización previa a journeys o envíos
- simulación parcial de estructuras relacionales

# Límites y riesgos

- no es SQL Server completo aunque comparta bastante sintaxis
- rendimiento y compatibilidad dependen del tamaño y forma de los datasets
- las subqueries y deduplicaciones pueden introducir coste alto o duplicados inesperados
- aliases complejos, palabras reservadas y ciertos formatos requieren cuidado especial

# Buenas prácticas

- reducir dataset lo antes posible
- validar claves de join y riesgo de multiplicidad
- documentar supuestos de unicidad
- separar queries funcionales de queries de diagnóstico

# Relación con otros documentos

- `patterns/2026-05-27-pattern-sfmc-service-cloud-aliases.md`
- `snippets/2026-05-27-sql-voucher-order-service-cloud-simulation.md`
