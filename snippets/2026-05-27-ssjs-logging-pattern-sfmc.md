---
type: snippet
title: SSJS logging pattern SFMC
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, logging, troubleshooting]
status: canonical
language: javascript
---

# Uso

```javascript
try {
  logsDE.Rows.Add({
    contactkey: accepted[a],
    eventDate: Now(),
    type: 'OptOut - Transac',
    status: 'ACCEPTED_BY_API'
  });
} catch (logEx) {
  Write("<br>Error logging ACCEPTED_BY_API: " + Stringify(logEx));
}
```

# Notas

- Registrar también los errores de logging mejora mucho la trazabilidad
- `Write()` es útil durante estabilización, pero conviene revisar su volumen en ejecuciones masivas
