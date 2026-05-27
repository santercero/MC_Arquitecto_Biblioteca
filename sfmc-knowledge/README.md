# SFMC Knowledge

Biblioteca maestra de Salesforce Marketing Cloud orientada a resolver dudas funcionales, técnicas, operativas y arquitectónicas con la mayor cobertura y portabilidad posible.

## Objetivo

Construir una base de conocimiento privada, curada y reutilizable que combine:

- conocimiento general de SFMC
- comportamiento real observado en runtime
- patrones y anti-patrones
- documentación oficial y comunitaria
- conocimiento específico del proyecto MC Arquitecto

## Principios

- No intentar guardar solo enlaces, sino conocimiento destilado
- Separar claramente fuente oficial, comunidad, observación real e hipótesis
- Favorecer Markdown y documentos canónicos estables
- Mantener trazabilidad de origen y estado de validación

## Grandes áreas

- `official/` documentación y notas derivadas de fuentes oficiales
- `community/` conocimiento curado desde comunidad y blogs reputados
- `patterns/` patrones reutilizables y anti-patrones
- `architecture/` modelos, decisiones y mapas de capacidades
- `troubleshooting/` fallos reales, edge cases y guías de diagnóstico
- `internals/` límites, rarezas, comportamientos no documentados
- `unknowns/` dudas abiertas y temas pendientes de validar
- `project-specific/` conocimiento propio de MC Arquitecto y casos concretos

## Estados recomendados

- `draft`
- `reviewed`
- `canonical`
- `needs-validation`
- `deprecated`

## Regla clave

Cuando una fuente diga una cosa y la práctica muestre otra, conservar ambas:
- lo que dice la fuente
- lo que se observó realmente
- el contexto exacto de la observación
