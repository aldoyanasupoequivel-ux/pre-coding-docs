# Guion Operativo y Casos de Uso del Sistema: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Plataforma:** {{Web / PWA / App Móvil (iOS & Android) / Full-Stack}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  
**Estado:** Especificación Operativa (Borrador / Aprobado)  

---

## 1. Introducción y Propósito

Define en 1–2 párrafos qué problema real resuelve **{{NOMBRE_PROYECTO}}**, quién lo usa en el día a día y cuáles son las prioridades operativas clave (ej. velocidad, simplicidad, trabajo offline, privacidad, trazabilidad).

---

## 2. Actores y Modelo de Acceso (RBAC)

Describe el punto de acceso (Login único, OAuth, biometría, acceso público + autenticado, etc.) y los permisos exactos por rol:

| Rol | Alcance en el Sistema | Restricciones de Seguridad |
| :--- | :--- | :--- |
| **{{Rol 1}}** | {{Operaciones permitidas en el día a día}} | **No tiene acceso a:** {{funciones o datos restringidos}} |
| **{{Rol 2}}** | {{Gestión integral, reportes, configuración}} | {{Alcance / auditoría}} |

---

## 3. Mapa de Flujos Operativos (End-to-End)

```text
┌────────────────────────────────────────────────────────────────────────┐
│                    MAPA DE FLUJOS - {{NOMBRE_PROYECTO}}                │
└────────────────────────────────────────────────────────────────────────┘
  [Inicio / Acceso]
         │
         ▼
  [Escenario 1: {{Nombre}}]
         │
         ├──────────────────────────┬──────────────────────────┐
         ▼                          ▼                          ▼
  [Escenario 2: {{Nombre}}]  [Escenario 3: {{Nombre}}]  [Escenario 4: {{Nombre}}]
         │                          │                          │
         └──────────────────────────┴──────────────────────────┘
                                    │
                                    ▼
                           [Escenario N: {{Cierre / Supervisión}}]
```

---

## 4. Guion de Casos de Uso Paso a Paso

### ESCENARIO 1: {{Nombre del Escenario}}
* **Actor(es):** {{Rol(es)}}
* **Precondiciones:** {{Estado previo requerido, ej. sesión iniciada, conectividad o modo offline}}
* **Flujo Principal (Paso a Paso):**
  1. {{Paso 1}}
  2. {{Paso 2}}
  3. {{Paso 3}}
* **Casos Alternativos / Estados Visuales / Excepciones:**
  * **Caso A ({{Estado positivo}}):** {{Comportamiento y acción disponible}}
  * **Caso B ({{Advertencia / Estado límite}}):** {{Comportamiento y acción disponible}}
  * **Caso C ({{Error / Bloqueo}}):** {{Comportamiento sin romper la experiencia}}

*(Repetir para cada escenario crítico del negocio.)*

---

## 5. Decisiones de Alcance del MVP (Qué SÍ y Qué NO entra en v1)

| Decisión | Qué se hace en v1 (MVP) | Qué queda explícitamente fuera (Futuro) | Justificación |
| :--- | :--- | :--- | :--- |
| **{{Área 1}}** | {{Solución simple y rápida}} | {{Funcionalidad pospuesta}} | {{Ahorro de tiempo, costo o fricción}} |
| **{{Área 2}}** | {{Solución simple y rápida}} | {{Funcionalidad pospuesta}} | {{Motivo operativo o técnico}} |
