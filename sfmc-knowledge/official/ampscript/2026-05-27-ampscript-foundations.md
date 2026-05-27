---
type: reference
title: AMPscript foundations
date: 2026-05-27
source: ampscript.guide plus general SFMC practice
status: reviewed
evidence: community-confirmed
tags: [sfmc, amscript, personalization, scripting]
---

# Resumen

AMPscript es el lenguaje principal de personalización y lógica embebida en Salesforce Marketing Cloud para emails, CloudPages, SMS y otros contextos de renderizado.

# Capacidades clave

- personalización con atributos
- acceso a Data Extensions
- lógica condicional
- manipulación de cadenas y fechas
- integración con objetos y datos relacionados
- soporte a casos transaccionales simples

# Límites y riesgos

- el contexto de ejecución importa mucho, preview no equivale a envío real
- algunas funciones temporales pueden comportarse distinto según contexto
- mezclar demasiada lógica de negocio en el contenido dificulta debugging y mantenimiento
- hay funciones y patrones cuyo comportamiento real difiere de lo que muchos ejemplos online sugieren

# Buenas prácticas

- mantener la lógica lo más simple y predecible posible
- separar personalización, acceso a datos y control de errores cuando se pueda
- validar siempre valores vacíos o nulos
- documentar edge cases observados en runtime

# Relación con otros documentos

- `sfmc-knowledge/troubleshooting/ampscript/`
- `patterns/2026-05-27-pattern-claimrow-single-coupon-assignment.md`
- `snippets/2026-05-27-ampscript-claimrow-coupon-assignment.md`
