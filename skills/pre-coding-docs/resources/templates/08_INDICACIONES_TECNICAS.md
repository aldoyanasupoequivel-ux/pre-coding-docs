# Indicaciones Técnicas, Buenas Prácticas y Flujo Git: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Propósito

Reglas obligatorias de ingeniería para desarrolladores humanos y asistentes de IA que trabajen en **{{NOMBRE_PROYECTO}}**.

---

## 2. Directrices de UI/UX y Dominio

* **Cero emojis en la interfaz:** usar únicamente iconos vectoriales (`{{Lucide / Heroicons / Material / SF Symbols}}`). *Excepción:* mensajes salientes hacia el usuario final (WhatsApp/Email/Push) si el negocio lo define.
* **Terminología oficial del negocio:** usar siempre el glosario del dominio (`{{Término 1}}`, `{{Término 2}}`, moneda `{{Moneda}}`) y evitar mensajes genéricos.

---

## 3. Estándares de Codificación y Arquitectura

* **Separación de responsabilidades:**
  * Capa de servicios/datos (`*.service.*` / `repositories/`): solo consultas a BD/API, nunca manipula UI.
  * Capa de presentación (`*.view.*` / `screens/` / `components/`): solo renderizado y eventos.
* **Tamaño controlado:** evitar archivos monolíticos (> 250–300 líneas); modularizar por responsabilidad.
* **Sin código muerto ni logs de prueba:** prohibido dejar `console.log` / `print()` de depuración en producción.
* **Manejo defensivo de errores:** prohibidos bloques `catch` vacíos; mostrar feedback claro al usuario (toast/banner/snackbar).

---

## 4. Seguridad y Variables de Entorno

* **Cero credenciales en código o docs:** toda clave o URL privada va en `.env.local` (ignorado por Git) y documentada con placeholders en `.env.example`.
* **Validación en doble capa:** validar en cliente por UX y siempre en backend/BD por seguridad.

---

## 5. Flujo de Trabajo Git (GitHub Flow)

* **Rama `main` protegida:** prohibido hacer `push` directo de features a `main`; todo entra vía Pull Request.
* **Nomenclatura de ramas:**
  * `feat/HU-XX-descripcion-corta`
  * `fix/HU-XX-descripcion-bug`
  * `refactor/descripcion` | `docs/descripcion`
* **Conventional Commits:** `feat(modulo): ...`, `fix(modulo): ...`, `style(modulo): ...`, `test(modulo): ...`, `docs(modulo): ...`.
* **Vinculación de Issues:** incluir `Closes #X` en la descripción del PR.

---

## 6. Checklist Pre-PR

- [ ] Interfaz libre de emojis, usando iconos vectoriales.
- [ ] Sin `console.log` ni código comentado de prueba.
- [ ] Sin credenciales ni secretos expuestos.
- [ ] Arquitectura modular respetada (datos separados de UI).
- [ ] Pruebas automatizadas y criterios BDD/Gherkin verificados.
- [ ] Descripción del PR vinculada al Issue (`Closes #X`).
