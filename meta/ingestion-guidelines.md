# Guía de ingesta

## Opciones de entrada

### Opción A, recomendada al inicio
Pedir a ChatGPT un resumen estructurado del chat usando el prompt de exportación y guardar el resultado en `inbox/`.

### Opción B
Copiar la conversación o exportación bruta a `raw-chats/` y procesarla después.

### Opción C
Subir documentos relacionados, por ejemplo:
- PDFs
- documentos funcionales
- diagramas
- capturas
- especificaciones
- consultas SQL
- fragmentos AMPscript o SSJS

## Regla práctica

- Lo bruto o sin procesar va a `inbox/` o `raw-chats/`
- Lo ya destilado va a `summaries/`, `decisions/`, `patterns/`, `snippets/` o `playbooks/`

## Sobre documentos

Sí, el repositorio puede guardar documentos de muchos tipos.

Recomendación:
- Markdown para conocimiento vivo
- PDF solo como referencia o fuente
- imágenes en carpetas de apoyo si hacen falta
- evitar binarios grandes innecesarios
