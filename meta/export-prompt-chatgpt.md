# Prompt de exportación para chats de ChatGPT

Usa este prompt al final de una conversación que quieras convertir en conocimiento reusable.

## Recomendación

Para copiar y pegar con menos pérdidas, usa un formato de salida en texto estructurado, no una respuesta libre. Eso reduce errores al copiar bloques, enlaces o snippets.

## Prompt base, robusto para copiar

```txt
Quiero que conviertas esta conversación en un paquete de conocimiento portable para mi biblioteca "MC Arquitecto".

Devuélveme la respuesta en español, en TEXTO PLANO estructurado, sin tablas, sin numeración automática y sin adornos. Usa exactamente estas claves en mayúsculas y en este orden:

TITULO:
FECHA:
TIPO:
FUENTE:
TAGS:

RESUMEN_EJECUTIVO:
CONTEXTO_Y_PROBLEMA:
SOLUCION_PROPUESTA:
DECISIONES_TOMADAS:
PASOS_DE_IMPLEMENTACION:
SNIPPETS_DE_CODIGO:
RIESGOS_O_ADVERTENCIAS:
BUENAS_PRACTICAS:
ARCHIVOS_SUGERIDOS:
REFERENCIAS:
REFERENCIAS_PENDIENTES:

Reglas:
- No repitas toda la conversación, destila solo lo útil.
- Si hay varias alternativas, sepáralas con guiones simples.
- Si hay código, envuélvelo con marcadores literales [SNIPPET:lenguaje] y [/SNIPPET].
- Si hay enlaces o nombres de documentos, no los resumas ni los reformatees.
- Si falta una referencia, escríbela en REFERENCIAS_PENDIENTES.
- En ARCHIVOS_SUGERIDOS, devuelve rutas concretas de archivo.
- Si detectas un patrón reutilizable, sepáralo de la solución concreta.
- Si detectas una decisión arquitectónica, añádela aunque no se haya dicho con esas palabras.
- No uses Markdown salvo dentro de snippets si es imprescindible.
```

## Variante corta

```txt
Destila este chat para mi biblioteca "MC Arquitecto" en texto plano estructurado. Usa las claves TITULO, FECHA, RESUMEN_EJECUTIVO, CONTEXTO_Y_PROBLEMA, SOLUCION_PROPUESTA, DECISIONES_TOMADAS, PASOS_DE_IMPLEMENTACION, SNIPPETS_DE_CODIGO, RIESGOS_O_ADVERTENCIAS, BUENAS_PRACTICAS, ARCHIVOS_SUGERIDOS, REFERENCIAS y REFERENCIAS_PENDIENTES. Si hay código, usa [SNIPPET:lenguaje].
```

## Después de copiar

- Si la salida viene ya muy limpia, guárdala en `inbox/chatgpt-export/`
- Si faltan referencias o ves texto raro, guárdala igualmente y marca lo pendiente
- Yo me encargo de convertirla a Markdown canónico y de recolocar piezas si están en la carpeta equivocada
