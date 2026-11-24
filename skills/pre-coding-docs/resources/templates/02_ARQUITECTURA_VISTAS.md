# Arquitectura de Vistas y Navegación: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Plataforma:** {{Web SPA / PWA / App Móvil iOS & Android / Web + Móvil}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Concepto y Enfoque de Navegación

Explica el paradigma de navegación según la plataforma:
* **Web / PWA:** SPA con barra superior o sidebar lateral, responsive en móvil.
* **App Móvil:** Bottom Tab Bar + Stack Navigation + Drawer/Modal Sheets + Deep Links (si aplica).

### Lógica de Aterrizaje Post-Login (Por Rol)
* **Si ingresa `{{Rol 1}}`:** Redirige a `{{Vista inicial}}` (y valida precondiciones como onboarding, permisos o apertura de turno).
* **Si ingresa `{{Rol 2}}`:** Redirige a `{{Vista inicial}}`.

---

## 2. Mapa Global de Navegación

```text
┌────────────────────────────────────────────────────────────────────────────┐
│  {{APP}}  |  [1. {{Vista 1}}]  [2. {{Vista 2}}]  [3. {{Vista 3}}]  [4. {{Vista 4}}*] │
└────────────────────────────────────────────────────────────────────────────┘
                                                            (* Exclusivo {{Rol}})
```

### Matriz de Acceso por Rol (RBAC)

| Vista / Módulo | Ruta / Screen | {{Rol 1}} | {{Rol 2}} | Propósito Principal |
| :--- | :--- | :---: | :---: | :--- |
| **1. {{Vista 1}}** | `/ruta-1` | ✅ Sí | ✅ Sí | {{Propósito}} |
| **2. {{Vista 2}}** | `/ruta-2` | ✅ Sí | ✅ Sí | {{Propósito}} |
| **3. {{Vista 3}}** | `/ruta-3` | ❌ No | ✅ Sí | {{Propósito}} |

---

## 3. Detalle de Vistas Principales

### VISTA 1: {{Nombre de la Vista}}
* **Objetivo:** {{Qué logra el usuario aquí y en cuánto tiempo}}
* **Elementos en Pantalla:**
  1. **{{Sección / Componente 1}}:** {{Descripción, campos, filtros}}
  2. **{{Sección / Componente 2}}:** {{Estados visuales: cargando, vacío, error, éxito}}
  3. **Acciones Principales:** {{Botones primarios y secundarios}}
* **Comportamiento Responsive / Móvil:** {{Adaptación en pantallas pequeñas, gestos o teclado}}

*(Repetir para cada vista principal.)*

---

## 4. Modales, Bottom Sheets y Flujos Emergentes

* **Modal / Sheet A — "{{Nombre}}":** {{Cuándo se abre, campos obligatorios/opcionales y resultado al confirmar}}
* **Modal / Sheet B — "{{Nombre}}":** {{Cuándo se abre, validaciones y resultado}}

---

## 5. Consideraciones Específicas de Móvil *(Omitir si es solo Web)*

* **Permisos del dispositivo:** {{Cámara, Ubicación, Notificaciones Push, Biometría — cuándo se solicitan}}
* **Estados sin conexión (Offline):** {{Qué vistas siguen funcionando sin internet y cómo se indica al usuario}}
* **Estados de ciclo de vida:** {{Comportamiento en background, deep links y notificaciones}}
