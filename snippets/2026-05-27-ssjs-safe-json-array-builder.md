---
type: snippet
title: SSJS safe JSON array builder
date: 2026-05-27
source: conversacion-tecnica-interna
tags: [sfmc, ssjs, json, payload-validation]
status: canonical
language: javascript
---

# Uso

```javascript
var payloadArray = [];

if (customerId && customerId.trim() !== "") {
  payloadArray.push(payloadObject);
} else {
  logsDE.Rows.Add({
    contactkey: phoneNumber,
    eventDate: Now(),
    type: 'OptOut - Transac',
    status: 'CUSTOMER_ID vacío'
  });
}

var payLoadRoot =
'{ "PhoneValidationReplies": [' +
payloadArray.join(',') +
'] }';
```

# Notas

- Evita concatenación insegura dentro del loop principal
- Sigue existiendo construcción final manual del string JSON, que podría evolucionar en el futuro
- Validar `null`, `undefined`, vacío y `trim()` antes de incorporar registros
