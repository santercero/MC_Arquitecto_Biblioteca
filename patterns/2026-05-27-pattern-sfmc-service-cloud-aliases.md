---
type: pattern
title: Patrón SQL SFMC para aliases jerárquicos estilo Service Cloud
date: 2026-05-27
source: conversacion-interna-mc-arquitecto
tags: [sfmc, sql, automation-studio, service-cloud, aliases, architecture]
status: canonical
---

# Problema

Necesidad de simular estructuras jerárquicas tipo Salesforce dentro de queries SQL de Marketing Cloud sin romper la sintaxis del motor SQL.

# Patrón propuesto

Usar aliases con formato jerárquico, por ejemplo `Order:Order_Contact__r:FirstName`, encapsulados entre corchetes `[]`, y mantener tablas sincronizadas con el esquema `ent.[Tabla]`.

# Cuándo usarlo

- Simulación de Entry Sources Salesforce
- Mapeos conceptuales entre SFMC y Service Cloud
- Queries que necesiten nombres de salida alineados con modelos jerárquicos conocidos

# Cuándo no usarlo

- Cuando la query vaya a consumirse en herramientas incompatibles con aliases complejos
- Cuando la prioridad sea simplicidad técnica por encima de compatibilidad semántica

# Ejemplo

Ver `snippets/2026-05-27-sql-voucher-order-service-cloud-simulation.md`.
