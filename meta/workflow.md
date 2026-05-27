# Flujo de actualización

## Entrada

Nuevos chats, notas o exportaciones llegan a:

- `inbox/`
- `raw-chats/`

## Procesado

Por cada conversación relevante:

1. Crear resumen en `summaries/`
2. Extraer decisiones a `decisions/`
3. Extraer patrones reutilizables a `patterns/`
4. Extraer snippets a `snippets/`
5. Crear playbook si hay un proceso repetible

## Mantenimiento

- Revisar duplicados
- Consolidar documentos parecidos
- Promover contenido estable a `canonical`
- Mantener índices por tema
