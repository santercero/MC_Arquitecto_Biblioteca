---
type: reference
title: Journey Builder foundations
date: 2026-05-27
source: general SFMC practice
status: draft
evidence: community-confirmed
tags: [sfmc, journey-builder, orchestration, segmentation, automation]
---

# Resumen

Journey Builder es la capa de orquestación de experiencias y comunicaciones en SFMC. Su potencia depende mucho de la calidad del modelo de datos, la definición de entradas y la coordinación con automatizaciones externas.

# Capacidades clave

- orquestación multistep
- decisiones y waits
- entradas basadas en eventos o audiencias
- coordinación con email, SMS y otros canales

# Límites y riesgos

- journeys complejos se vuelven opacos si no hay diseño disciplinado
- las entradas y reentradas mal definidas generan duplicados o silencios
- muchas incidencias vienen del dato previo, no del journey en sí

# Buenas prácticas

- diseñar entradas limpias y bien deduplicadas
- evitar meter lógica de negocio excesiva dentro del journey
- documentar reglas de reentry, exit y audiencias
- apoyarse en preprocesado SQL o automatizaciones cuando convenga

# Relación con otros documentos

- `sfmc-knowledge/patterns/journeys/`
- `sfmc-knowledge/troubleshooting/journeys/`
