---
type: decision
title: Usar aliases estilo Service Cloud en queries SQL de SFMC
date: 2026-05-27
source: conversacion-interna-mc-arquitecto
tags: [sfmc, sql, service-cloud, aliases, architecture]
status: canonical
---

# Decisión

Mantener aliases jerárquicos estilo Service Cloud en queries SQL de SFMC, encapsulándolos entre corchetes `[]`.

# Contexto

Se necesitaba emular la estructura de un Entry Source Salesforce dentro de Marketing Cloud, pero aliases como `Order:Order_Contact__r:FirstName` producían errores de sintaxis al no escaparse correctamente.

# Motivo

- Preserva compatibilidad semántica con modelos Salesforce
- Facilita la lectura funcional por parte de equipos acostumbrados a Service Cloud
- Evita simplificaciones que rompen la equivalencia conceptual con Entry Sources

# Consecuencias

- Se adopta `[]` como regla obligatoria para aliases complejos
- Hay que vigilar compatibilidad y límites en herramientas concretas de SFMC
- El equipo debe mantener consistencia de nomenclatura entre SQL, Journey Builder y AMPscript

# Alternativas consideradas

- Simplificar aliases a nombres planos
- Renombrar campos para evitar `:` o palabras reservadas
- Mantener una estructura menos fiel a Salesforce pero más genérica
