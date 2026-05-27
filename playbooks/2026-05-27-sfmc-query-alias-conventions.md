---
type: playbook
title: Convenciones de aliases SQL en SFMC para estructuras estilo Salesforce
date: 2026-05-27
source: conversacion-interna-mc-arquitecto
tags: [sfmc, sql, aliases, service-cloud, playbook]
status: draft
---

# Objetivo

Definir una convención consistente para aliases SQL en SFMC cuando se quiera emular estructura semántica de Salesforce.

# Prerrequisitos

- Query Activity o entorno SQL de SFMC
- Tablas sincronizadas accesibles con prefijo `ent.`
- Criterio claro de cuándo conviene emular una estructura jerárquica

# Pasos

1. Definir los nombres de salida alineados con la semántica Salesforce
2. Encerrar siempre aliases complejos entre corchetes `[]`
3. Mantener `ent.[Tabla]` para synchronized data extensions
4. Reducir dataset antes de introducir subqueries o joins pesados
5. Revisar si hay riesgo de empates en `CreatedDate`
6. Validar la query en el contexto real donde vaya a ejecutarse

# Validación

- La query compila sin errores de sintaxis
- Los nombres de salida mantienen la semántica esperada
- El rendimiento es aceptable para el tamaño del dataset

# Errores frecuentes

- No encapsular aliases con `:`
- Romper consistencia de nomenclatura entre sistemas
- Ignorar el coste de subqueries correlacionadas
