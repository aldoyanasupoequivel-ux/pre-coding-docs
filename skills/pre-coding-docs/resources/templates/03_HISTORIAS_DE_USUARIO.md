# Product Backlog: Historias de Usuario — {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Convenciones

Cada Historia de Usuario (HU) es auto-contenida e incluye:
* **Formato narrativo:** `Como [rol], quiero [acción], para [beneficio]`.
* **Especificaciones técnicas y de UI:** validaciones, flujos y persistencia.
* **Criterios de aceptación (BDD / Gherkin):** `Dado que... Cuando... Entonces...`.
* **Priorización MoSCoW:** `Must Have` | `Should Have` | `Could Have`.

---

## 2. Mapa de Épicas del Sistema

```text
┌────────────────────────────────────────────────────────────────────────┐
│                   MAPA DE ÉPICAS - {{NOMBRE_PROYECTO}}                 │
└────────────────────────────────────────────────────────────────────────┘
  ÉPICA 1: {{Nombre de Épica 1}}
       │── HU-01: {{Título}}
       │── HU-02: {{Título}}
       │
  ÉPICA 2: {{Nombre de Épica 2}}
       │── HU-03: {{Título}}
       │── HU-04: {{Título}}
```

---

## 3. Especificación Detallada de Historias de Usuario

### ÉPICA 1: {{NOMBRE DE ÉPICA}}

#### HU-01: {{Título de la Historia}}
* **ID:** `HU-01`
* **Prioridad:** Must Have
* **Descripción:**
  * **Como** {{rol}},
  * **Quiero** {{acción concreta}},
  * **Para** {{beneficio medible}}.
* **Especificaciones Técnicas y de UI:**
  1. {{Regla de UI / campos / validaciones}}
  2. {{Regla de negocio / backend / persistencia}}
  3. {{Seguridad / permisos / manejo de errores}}
* **Criterios de Aceptación:**
  * **Escenario 1 ({{Camino feliz}}):**
    * **Dado que** {{contexto inicial}},
    * **Cuando** {{acción del usuario}},
    * **Entonces** {{resultado observable esperado}}.
  * **Escenario 2 ({{Validación o caso borde}}):**
    * **Dado que** {{contexto de error}},
    * **Cuando** {{acción del usuario}},
    * **Entonces** {{respuesta controlada del sistema}}.

*(Repetir para cada HU del backlog.)*

---

## 4. Matriz Resumen del Product Backlog

| ID | Épica | Título de la Historia | Prioridad | Story Points |
| :---: | :--- | :--- | :---: | :---: |
| **HU-01** | {{Épica 1}} | {{Título}} | Must | {{pts}} |
| **HU-02** | {{Épica 1}} | {{Título}} | Must | {{pts}} |
| **TOTAL** | — | **{{N}} Historias de Usuario** | — | **{{Total}}** |
