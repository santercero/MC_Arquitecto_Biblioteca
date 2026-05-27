---
type: reference
title: Data Extensions and Data Views foundations
date: 2026-05-27
source: general SFMC practice
status: draft
evidence: community-confirmed
tags: [sfmc, data-extensions, data-views, model, segmentation]
---

# Resumen

Data Extensions son la base práctica de almacenamiento y segmentación en SFMC. Data Views exponen información del sistema útil para reporting, tracking y lógica operativa.

# Capacidades clave

- almacenamiento estructurado para campañas y procesos
- staging intermedio para automatizaciones
- soporte a segmentación, audiencias y trazabilidad
- consulta de métricas y eventos mediante Data Views

# Límites y riesgos

- los modelos se degradan rápido si no hay gobierno de claves y naming
- no todas las necesidades analíticas encajan bien en Data Views
- hay límites de retención, disponibilidad y contexto según vista o entorno

# Buenas prácticas

- definir claves y propósito antes de crear una DE
- distinguir DE transaccional, staging, log y audiencia
- documentar retención y ownership
- tratar Data Views como fuente útil pero no universal

# Relación con otros documentos

- `sfmc-knowledge/architecture/`
- `sfmc-knowledge/patterns/data-model/`
