# Prompt de exportación para chats de ChatGPT

Usa este prompt al final de una conversación que quieras convertir en conocimiento reusable.

## Prompt base

```txt
Quiero que conviertas esta conversación en un paquete de conocimiento portable para mi biblioteca "MC Arquitecto".

Devuélveme la respuesta en español y en formato Markdown, con estas secciones exactas:

1. Titulo
2. Fecha
3. Resumen ejecutivo
4. Contexto y problema
5. Solución propuesta
6. Decisiones tomadas
7. Pasos de implementación
8. Snippets de código
9. Riesgos, límites o advertencias
10. Buenas prácticas
11. Tags sugeridos
12. Archivos sugeridos en mi repositorio

Reglas:
- No repitas toda la conversación, destila solo lo útil.
- Si hay varias alternativas, sepáralas claramente.
- Si hay código, entrégalo en bloques Markdown con lenguaje.
- Si faltan datos, indícalo explícitamente.
- En "Archivos sugeridos en mi repositorio", indica en qué carpeta debería guardarse cada parte, por ejemplo:
  - summaries/...
  - decisions/...
  - patterns/...
  - snippets/...
  - playbooks/...
- Si detectas un patrón reutilizable, sepáralo de la solución concreta.
- Si detectas una decisión arquitectónica, añádela aunque no se haya dicho con esas palabras.
```

## Variante corta

```txt
Destila este chat para mi biblioteca "MC Arquitecto" en Markdown. Extrae resumen, decisiones, patrón reutilizable, pasos, snippets, riesgos y tags. Indica también en qué archivos/carpeta debería guardarlo dentro del repositorio.
```
