# Pre-Coding Docs - plugin de Antigravity

Plugin modular que combina:
1. **Skill interactivo (`pre-coding-docs`)**: te entrevista antes de programar y genera hasta **12 documentos Markdown** coherentes entre sí para cualquier sistema **Web, PWA o Móvil**.
2. **Reglas de ingeniería (`rules/AGENTS.md`)**: asegura buenas prácticas durante el desarrollo (arquitectura modular, UI limpia sin emojis, cero credenciales expuestas, manejo defensivo de errores y Git Flow) y te ofrece iniciar la entrevista cuando detecta un proyecto nuevo.

---

## Estructura del plugin

```text
pre-coding-docs/
├── plugin.json                              # Manifiesto del plugin
├── README.md                                # Esta guía
├── rules/
│   └── AGENTS.md                            # Reglas de codificación + activación proactiva
└── skills/
    └── pre-coding-docs/
        ├── SKILL.md                         # Flujo interactivo (entrevista -> generación -> auditoría)
        ├── references/
        │   └── consistency-checklist.md     # Auditoría cruzada pre-código
        └── resources/
            └── templates/                   # 12 plantillas Markdown universales (Web + Móvil)
                ├── 01_GUION_OPERATIVO.md
                ├── 02_ARQUITECTURA_VISTAS.md
                ├── 03_HISTORIAS_DE_USUARIO.md
                ├── 04_PLANIFICACION_SPRINTS.md
                ├── 05_STACK_Y_ARQUITECTURA.md
                ├── 06_MODELO_BASE_DE_DATOS.md
                ├── 07_SISTEMA_DISENO_VISUAL.md
                ├── 08_INDICACIONES_TECNICAS.md
                ├── 09_CONTRATOS_API_INTEGRACIONES.md
                ├── 10_ESTRATEGIA_TESTING_QA.md
                ├── 11_DESPLIEGUE_Y_CICD.md
                └── 12_BACKUPS_Y_MIGRACION.md
```

---

## Cómo usarlo en Antigravity

Una vez ubicado en `~/.gemini/config/plugins/pre-coding-docs/`, **el plugin se carga y activa automáticamente** para todos tus proyectos (no necesitas comandos extra de activación). Puedes verificarlo o encenderlo/apagarlo en cualquier momento desde el panel de **Customizations** de Antigravity.

### Formas de iniciar la entrevista en un proyecto nuevo

1. **Activación automática (sin invocar el plugin):**
   Abre una carpeta vacía para tu nuevo proyecto y describe qué vas a construir, por ejemplo:
   - *"Quiero crear una app móvil para reservas de canchas deportivas"*
   - *"Vamos a iniciar un sistema web de inventario para una ferretería"*

   Al detectar un proyecto nuevo sin carpeta `docs/`, la regla global (`rules/AGENTS.md`) se dispara automáticamente y el agente te ofrecerá iniciar la entrevista de `pre-coding-docs` antes de codificar.

2. **Invocación directa:**
   Si prefieres arrancar la entrevista de inmediato, escribe:
   - *"Iniciemos un nuevo proyecto con `pre-coding-docs`"*
   - *"Usa `pre-coding-docs` y hazme la entrevista para documentar mi sistema"*

### Qué ocurre al iniciarlo

1. **Ronda 1 (opción múltiple):** tipo de plataforma (Web/PWA, Móvil, combinado o API), alcance (los 12 documentos, paquete MVP o selección) y tipo de backend/BD.
2. **Rondas 2 y 3 (preguntas breves):** nombre del sistema, roles/permisos, flujos principales, exclusiones del MVP, stack y estilo visual.
3. **Generación en `docs/`:** crea los documentos Markdown adaptados dentro de la carpeta `docs/` del nuevo proyecto.
4. **Auditoría cruzada:** verifica coherencia entre roles, vistas, HUs, sprints y base de datos antes de iniciar el **Sprint 1** (donde las reglas de ingeniería limpia aplican automáticamente).

---
## Cómo actualizar el skill, las reglas o las plantillas

1. Edita directamente cualquier archivo dentro de esta carpeta:
   - Flujo de preguntas y generación: `skills/pre-coding-docs/SKILL.md`
   - Plantillas individuales: `skills/pre-coding-docs/resources/templates/*.md`
   - Reglas de código: `rules/AGENTS.md`
2. **Los cambios en Antigravity se aplican en el siguiente turno** (no necesitas reinstalar).
3. Guarda tus mejoras en GitHub:

```powershell
git add .
git commit -m "docs(templates): actualizar plantilla de arquitectura"
git push
```

### Instalar en otra PC desde tu GitHub

Si cambias de computadora, simplemente clona tu repositorio directamente en la carpeta global de plugins de Antigravity:

```powershell
git clone https://github.com/aldoyanasupoequivel-ux/pre-coding-docs.git "$HOME\.gemini\config\plugins\pre-coding-docs"
```
