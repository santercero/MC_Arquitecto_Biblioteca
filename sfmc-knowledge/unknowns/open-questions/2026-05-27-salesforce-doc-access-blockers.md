---
type: reference
title: Salesforce documentation access blockers from automated environment
date: 2026-05-27
source: direct fetch attempts from OpenClaw environment
status: needs-validation
evidence: observed-runtime
tags: [sfmc, salesforce, documentation, access, blocker, anti-bot]
---

# Resumen

Los intentos de acceso automatizado a documentación oficial de Salesforce Marketing Cloud desde este entorno están devolviendo errores 403 y páginas de bloqueo.

# Observado

- `web_fetch` devuelve 403 en múltiples rutas de developer.salesforce.com
- algunas páginas de help.salesforce.com cargan estado intermedio pero no contenido útil
- el navegador integrado no pudo probarse bien por restricciones del entorno actual

# Hipótesis

- protección anti-bot
- WAF/CDN con fingerprinting del entorno
- dependencia de JS, cookies o navegación interactiva real

# Opciones futuras

- usar navegador real del usuario si está disponible
- capturar páginas críticas manualmente cuando haga falta
- buscar mirrors o versiones alternativas accesibles
- seguir curando conocimiento desde fuentes accesibles mientras tanto
