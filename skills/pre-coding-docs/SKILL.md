---
name: pre-coding-docs
description: >-
  Interactive pre-coding documentation generator for any Web, PWA, Mobile, or Full-Stack
  software system. Use when starting a new software project, planning system architecture
  before writing code, or generating structured Markdown engineering blueprints (operational
  script, views, user stories, sprints, stack, database model, design system, coding
  standards, API contracts, testing strategy, CI/CD, and backups/migration).
---

# Pre-Coding Docs — Generador Interactivo de Documentación Pre-Código

Este skill guía al desarrollador a través de una **entrevista estructurada por rondas** y genera un paquete coherente de hasta **12 documentos Markdown** dentro de `docs/` en el proyecto actual, antes de escribir la primera línea de código.

---

## Principios de Ejecución

1. **Nunca asumas requisitos críticos en silencio:** pregunta siempre al usuario primero en rondas cortas y claras.
2. **Usa `ask_question` para decisiones de selección** (tipo de plataforma, alcance del paquete, arquitectura backend/BD, estrategia de despliegue) y **preguntas abiertas concisas** para el dominio del negocio, actores y flujos.
3. **Adaptación Web vs. Móvil:** ajusta automáticamente navegación, tokens de diseño, permisos del dispositivo, modo offline, almacenamiento y distribución (Web/PWA vs. App Store / Play Store).
4. **Cero secretos reales en Markdown:** usa siempre placeholders (`{{SUPABASE_URL}}`, `{{API_KEY}}`) y referencia `.env.example`.
5. **Trazabilidad cruzada obligatoria:** todos los documentos deben ser consistentes entre sí (los mismos roles, HUs, vistas, entidades y reglas).

---

## Fase 1: Entrevista de Descubrimiento (2 a 3 rondas breves)

No abrumes al usuario con 25 preguntas a la vez. Divide la entrevista en rondas cortas:

### Ronda 1 — Contexto Técnico y Alcance (usa `ask_question`)
Pregunta con opción múltiple:
1. **Tipo de plataforma:**
   - Web / PWA (Desktop + Responsive)
   - App Móvil (iOS / Android nativa o híbrida)
   - Web + App Móvil (ecosistema combinado)
   - Solo Backend / API
2. **Alcance de documentos a generar:**
   - Paquete Completo (los 12 documentos)
   - Paquete MVP Esencial (01 Guion, 02 Vistas, 03 HUs, 05 Stack, 06 Base de Datos, 07 Diseño)
   - Selección personalizada
3. **Tipo de backend y datos:**
   - BaaS Cloud (ej. Supabase / Firebase)
   - Backend propio + Base de Datos Relacional (PostgreSQL / MySQL)
   - Backend propio + NoSQL / Híbrido
   - Local-first / Offline-first (SQLite / sincronización)

### Ronda 2 — Negocio, Actores y Flujos Clave (preguntas abiertas breves)
Pide al usuario que responda brevemente (puede ser en viñetas o texto libre):
1. **Nombre del proyecto y problema que resuelve** (1–2 líneas).
2. **Actores / Roles del sistema** y qué puede o no puede hacer cada uno.
3. **Flujos principales del día a día** (los 3 a 7 escenarios críticos).
4. **Decisiones de alcance MVP:** ¿qué funcionalidades quedan **explícitamente fuera** de la versión 1?
5. **Integraciones externas** (si aplica): pagos, mensajería (WhatsApp/Email/SMS), notificaciones push, mapas, biometría, etc.

### Ronda 3 — Identidad Visual, Stack y Operación (solo lo que falte)
Si el usuario no lo mencionó aún, pregunta brevemente:
1. **Stack preferido** (o confirma si deseas que propongas el stack óptimo según costo y mantenibilidad).
2. **Identidad visual:** modo oscuro o claro, colores de marca, estilo visual deseado.
3. **Restricciones operativas:** presupuesto mensual objetivo (ej. capa gratuita vs. producción pagada), tamaño del equipo, plazos o duración de sprints.

> Si el usuario ya entregó un brief detallado o respondió varios puntos desde el inicio, **omite las preguntas ya respondidas** y confirma solo los vacíos.

---

## Fase 2: Generación Ordenada de Documentos en `docs/`

Lee las plantillas correspondientes en `./resources/templates/` y genera los archivos en el workspace del proyecto dentro de `docs/` siguiendo el **orden de dependencia** (puedes escribir varios en paralelo por lote):

### Lote 1 — Negocio y Experiencia
- `docs/01_GUION_OPERATIVO.md` ← plantilla [`01_GUION_OPERATIVO.md`](./resources/templates/01_GUION_OPERATIVO.md)
- `docs/02_ARQUITECTURA_VISTAS.md` ← plantilla [`02_ARQUITECTURA_VISTAS.md`](./resources/templates/02_ARQUITECTURA_VISTAS.md)
- `docs/03_HISTORIAS_DE_USUARIO.md` ← plantilla [`03_HISTORIAS_DE_USUARIO.md`](./resources/templates/03_HISTORIAS_DE_USUARIO.md)
- `docs/04_PLANIFICACION_SPRINTS.md` ← plantilla [`04_PLANIFICACION_SPRINTS.md`](./resources/templates/04_PLANIFICACION_SPRINTS.md)

### Lote 2 — Arquitectura, Datos y Diseño
- `docs/05_STACK_Y_ARQUITECTURA.md` ← plantilla [`05_STACK_Y_ARQUITECTURA.md`](./resources/templates/05_STACK_Y_ARQUITECTURA.md)
- `docs/06_MODELO_BASE_DE_DATOS.md` ← plantilla [`06_MODELO_BASE_DE_DATOS.md`](./resources/templates/06_MODELO_BASE_DE_DATOS.md)
- `docs/07_SISTEMA_DISENO_VISUAL.md` ← plantilla [`07_SISTEMA_DISENO_VISUAL.md`](./resources/templates/07_SISTEMA_DISENO_VISUAL.md)
- `docs/08_INDICACIONES_TECNICAS.md` ← plantilla [`08_INDICACIONES_TECNICAS.md`](./resources/templates/08_INDICACIONES_TECNICAS.md)

### Lote 3 — Integraciones, Calidad y Operación
- `docs/09_CONTRATOS_API_INTEGRACIONES.md` ← plantilla [`09_CONTRATOS_API_INTEGRACIONES.md`](./resources/templates/09_CONTRATOS_API_INTEGRACIONES.md)
- `docs/10_ESTRATEGIA_TESTING_QA.md` ← plantilla [`10_ESTRATEGIA_TESTING_QA.md`](./resources/templates/10_ESTRATEGIA_TESTING_QA.md)
- `docs/11_DESPLIEGUE_Y_CICD.md` ← plantilla [`11_DESPLIEGUE_Y_CICD.md`](./resources/templates/11_DESPLIEGUE_Y_CICD.md)
- `docs/12_BACKUPS_Y_MIGRACION.md` ← plantilla [`12_BACKUPS_Y_MIGRACION.md`](./resources/templates/12_BACKUPS_Y_MIGRACION.md)

*(Si el usuario eligió el paquete MVP o una selección personalizada, genera únicamente los archivos elegidos.)*

---

## Fase 3: Auditoría de Coherencia Cruzada

Antes de entregar el paquete al usuario, lee [`./references/consistency-checklist.md`](./references/consistency-checklist.md) y verifica cada punto sobre los documentos generados. Si detectas incoherencias (por ejemplo, una HU sin tabla que la respalde, un rol que aparece en `02` pero no en `06`, o una credencial real expuesta), corrígelas de inmediato.

---

## Fase 4: Entrega y Siguiente Paso

1. Muestra al usuario una tabla resumen con los documentos generados y sus enlaces clicables (`file://`).
2. Destaca las decisiones clave de arquitectura y cualquier supuesto que convenga revisar.
3. Pregunta si desea:
   - Ajustar algún documento específico, o
   - **Iniciar el Sprint 1** siguiendo las reglas de `docs/08_INDICACIONES_TECNICAS.md`.

---

## Mantenimiento y Actualización del Skill

Si el usuario pide modificar o mejorar estas plantillas o el flujo de entrevista, edita los archivos directamente dentro de este plugin (`~/.gemini/config/plugins/pre-coding-docs/`) y recuérdale que puede hacer `git commit && git push` para respaldar sus cambios en GitHub.
