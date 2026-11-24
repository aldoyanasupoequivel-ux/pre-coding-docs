# Pre-Coding Docs & Engineering Standards

## 1. Activación Proactiva en Proyectos Nuevos

Cuando el usuario inicie un **nuevo proyecto de software** (web, PWA, app móvil o backend) y el workspace todavía no cuente con documentación de diseño previo (por ejemplo, una carpeta `docs/` con especificación operativa, vistas, historias de usuario o modelo de datos):

- **Ofrece iniciar la entrevista de `pre-coding-docs`** antes de escribir código de producción, preguntando brevemente si desea:
  1. Generar el paquete completo (o una selección) de documentación previa mediante preguntas guiadas (`pre-coding-docs`), o
  2. Pasar directo a codificar un prototipo rápido.
- Si el usuario acepta documentar primero (o invoca directamente `pre-coding-docs`), activa el skill `pre-coding-docs` y sigue su entrevista estructurada paso a paso.
- Si el usuario pide explícitamente saltar la documentación o se trata de un script puntual / corrección en un proyecto existente, respeta su decisión sin insistir.

---

## 2. Estándares Obligatorios de Ingeniería (Web y Móvil)

Aplica estas reglas en todo código generado durante el desarrollo:

### 2.1 Interfaz de Usuario (UI/UX) Profesional
- **Cero emojis en la interfaz:** No uses emojis en botones, menús, encabezados, tablas o alertas de la app. Usa **iconos vectoriales limpios** (SVG / Lucide / Heroicons / Material Symbols / SF Symbols según la plataforma).
  - *Excepción:* Mensajes salientes hacia canales externos del usuario final (WhatsApp, SMS, notificaciones push o correos comerciales) si el negocio lo solicita.
- **Lenguaje de dominio real:** Evita textos genéricos (*"Operación exitosa"*, *"Item guardado"*) o mezclas de idiomas no solicitadas. Usa siempre la terminología exacta definida en el guion operativo del proyecto.
- **Accesibilidad mínima:** Mantén contraste legible (WCAG AA) y áreas táctiles cómodas (mínimo `44px` / `48dp` en controles interactivos).

### 2.2 Arquitectura Modular y Código Limpio
- **Prohibido el código monolítico:** Separa estrictamente la capa de datos/servicios (`*.service.*` / `repositories/`) de la capa de presentación/interfaz (`*.view.*` / `screens/` / `components/`). Evita archivos gigantes que mezclen consultas a BD/API con renderizado de UI.
- **Organización por características (*Feature-based*):** Agrupa el código por módulo de negocio (`auth`, `users`, `billing`, etc.) antes que por tipo de archivo cuando el proyecto crece.
- **Sin residuos de depuración:** No dejes `console.log`, `print()` de prueba ni código comentado muerto antes de dar una tarea por terminada.

### 2.3 Seguridad y Manejo de Datos
- **Cero credenciales en el código o en la documentación:** Nunca escribas API keys, tokens, contraseñas o URLs privadas en código fuente ni en archivos `.md`. Usa siempre variables de entorno y documenta solo `.env.example` con placeholders.
- **Fuente única de verdad:** No guardes datos críticos de negocio únicamente en `localStorage` / `sessionStorage` cuando existe una base de datos central (salvo caché offline explícitamente diseñada en apps móviles/PWA con estrategia de sincronización).
- **Manejo defensivo de errores:** Prohibidos los bloques `catch` vacíos o silenciosos. Toda operación asíncrona o de red debe capturar errores, registrarlos adecuadamente y mostrar retroalimentación clara al usuario.

### 2.4 Flujo de Trabajo Git y Entregables
- **Rama principal protegida (`main`):** Trabaja nuevas funcionalidades y correcciones en ramas dedicadas (`feat/HU-XX-descripcion`, `fix/HU-XX-descripcion`, `refactor/...`) integradas vía Pull Request.
- **Commits convencionales:** Usa el formato `tipo(alcance): descripcion breve` (`feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`).
- **Trazabilidad:** Vincula cada PR o entrega a la Historia de Usuario / Issue correspondiente y verifica sus criterios de aceptación antes de marcarla como terminada.
