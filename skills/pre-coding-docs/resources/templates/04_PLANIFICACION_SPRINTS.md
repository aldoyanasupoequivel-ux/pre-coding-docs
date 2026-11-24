# Planificación de Sprints: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  
**Tablero de Seguimiento:** {{URL de GitHub Projects / Jira / Linear / Trello}}  

---

## 1. Visión General del Plan Ágil

```text
┌────────────────────────────────────────────────────────────────────────┐
│                       CRONOGRAMA DE SPRINTS                            │
└────────────────────────────────────────────────────────────────────────┘
  [ SPRINT 1: {{Cimientos y Seguridad}} ] ──► {{Fechas}} ({{N}} HUs)
         │
         ▼
  [ SPRINT 2: {{Núcleo Operativo}} ]      ──► {{Fechas}} ({{N}} HUs)
         │
         ▼
  [ SPRINT 3: {{Integraciones y Cierre}} ]──► {{Fechas}} ({{N}} HUs)
         │
         ▼
  [ RELEASE / PUBLICACIÓN EN PRODUCCIÓN ]
```

---

## 2. Definición de Hecho (Definition of Done - DoD)

Una Historia de Usuario se considera **Done** únicamente cuando cumple con:
1. **Funcionalidad Completa:** Pasa el 100% de sus criterios de aceptación BDD/Gherkin.
2. **Seguridad y Permisos:** Rutas, endpoints y consultas respetan RBAC y validaciones.
3. **Persistencia y Errores:** Datos verificados sin duplicados y manejo defensivo ante fallos de red.
4. **Calidad Visual y Dispositivos:** Verificado en los tamaños de pantalla / dispositivos objetivo.
5. **Pruebas y Merge:** Tests pasando, revisión de PR aprobada y fusionado en `main` cerrando el Issue.

---

## 3. Detalle de Sprints

### SPRINT 1: "{{Nombre del Sprint}}"
* **Duración:** {{Fechas / Días}}
* **Story Points:** {{pts}}
* **Sprint Goal:** *{{Objetivo único y medible del sprint}}*

| Issue | Código | Título | Épica | Prioridad |
| :---: | :---: | :--- | :--- | :---: |
| `#1` | **HU-01** | {{Título}} | {{Épica}} | Must |

**Entregables Técnicos del Sprint 1:**
1. {{Entregable 1}}
2. {{Entregable 2}}

*(Repetir para cada Sprint planificado.)*

---

## 4. Matriz de Resumen y Capacidad

| Sprint | Fechas | Objetivo Principal | HUs Asignadas | Story Points | Estado |
| :---: | :---: | :--- | :---: | :---: | :---: |
| **Sprint 1** | {{Fechas}} | {{Objetivo}} | {{N}} HUs | {{pts}} | Planificado |
| **TOTAL** | **{{Duración}}** | **MVP Completo en Producción** | **{{Total}} HUs** | **{{Total}} pts** | — |
