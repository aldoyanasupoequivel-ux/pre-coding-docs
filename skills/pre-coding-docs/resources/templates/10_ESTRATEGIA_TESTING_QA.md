# Estrategia de Testing y Aseguramiento de Calidad (QA): {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Plataforma:** {{Web / PWA / App Móvil}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Pirámide de Pruebas y Herramientas

| Nivel | Qué se valida | Herramienta Sugerida | Cuándo se ejecuta |
| :--- | :--- | :--- | :--- |
| **Unitarias** | Reglas de negocio puras, cálculos, validadores y formateadores | {{Vitest / Jest / Flutter Test / Pytest}} | Local + cada PR |
| **Integración** | Servicios + API / Base de datos, permisos RBAC/RLS | {{Supertest / Testing Library / Testcontainers}} | Cada PR |
| **E2E (Flujos Críticos)** | Escenarios clave de `01_GUION_OPERATIVO.md` | {{Playwright / Cypress / Maestro / Detox}} | Pre-release / `main` |

---

## 2. Matriz de Cobertura Crítica (Mapeada a HUs)

| HU | Flujo / Regla Crítica | Tipo de Prueba | Criterio de Éxito |
| :---: | :--- | :---: | :--- |
| **HU-01** | Login, redirección por rol y bloqueo de rutas no autorizadas | Integración + E2E | HTTP 403 / redirección efectiva |
| **HU-XX** | {{Cálculo crítico o validación principal}} | Unitaria | 100% de casos borde cubiertos |

---

## 3. Pruebas No Funcionales y de Dispositivos

* **Web / PWA:** Chrome, Edge y Safari móvil; verificación responsive (`375px`, `768px`, `1280px+`).
* **App Móvil *(si aplica)*:** iOS y Android físicos/emuladores, permisos denegados, modo avión/offline, rotación y teclado virtual.
* **Seguridad básica:** pruebas de acceso cruzado entre roles, sanitización de entradas y verificación de cero secretos en el bundle.

---

## 4. Criterios de Salida a Producción (Go / No-Go)

- [ ] 100% de pruebas unitarias y de integración en verde.
- [ ] Cero bugs de severidad Crítica o Alta abiertos.
- [ ] Flujos `Must Have` verificados en entorno Preview / Staging.
