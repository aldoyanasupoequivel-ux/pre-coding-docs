# Pre-Coding Docs — Plugin de Antigravity

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

## Cómo subir este plugin a tu GitHub

Para versionar este plugin en tu cuenta de GitHub:

1. Crea un repositorio nuevo en GitHub (por ejemplo, `pre-coding-docs`), **sin** README ni `.gitignore` iniciales.
2. Abre una terminal en esta carpeta (`C:\Users\aldin\.gemini\config\plugins\pre-coding-docs`) y ejecuta:

```powershell
git init -b main
git add .
git commit -m "feat: plugin inicial pre-coding-docs con 12 plantillas y reglas"
git remote add origin https://github.com/<TU_USUARIO>/pre-coding-docs.git
git push -u origin main
```

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
git clone https://github.com/<TU_USUARIO>/pre-coding-docs.git "$HOME\.gemini\config\plugins\pre-coding-docs"
```
