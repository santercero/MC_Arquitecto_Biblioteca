---
type: snippet
title: SSJS OAuth client credentials SFMC
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, oauth, azure, api-integration]
status: draft
language: javascript
---

# Uso

```javascript
if (statusCode === 202) {
  var response = Platform.Function.ParseJSON(result.Response[0]);
  var accepted = response.accepted;
  var rejected = response.rejected;
}
```

# Notas

- Este snippet refleja solo un fragmento del flujo observado
- Falta documentar el bloque completo de autenticación OAuth `client_credentials`
- Mantener especial cuidado con secretos hardcodeados
