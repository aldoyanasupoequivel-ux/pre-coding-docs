# Modelo y Diseño de Base de Datos: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Motor de Base de Datos:** {{PostgreSQL / MySQL / SQLite / NoSQL}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Diagrama Entidad-Relación (ERD)

```mermaid
erDiagram
    USUARIOS ||--o{ {{ENTIDAD_PRINCIPAL}} : "gestiona"

    USUARIOS {
        uuid id PK
        varchar nombre_completo
        varchar email UK
        varchar rol
        varchar estado
        timestamptz creado_en
        timestamptz eliminado_en
    }

    {{ENTIDAD_PRINCIPAL}} {
        uuid id PK
        uuid creado_por FK
        varchar estado
        timestamptz creado_en
        timestamptz actualizado_en
    }
```

---

## 2. Diccionario de Datos y Reglas de Integridad

### 2.1 Tabla / Colección: `usuarios`
| Campo | Tipo | Nulo | Restricción / Default | Regla de Negocio |
| :--- | :--- | :---: | :--- | :--- |
| `id` | `UUID` | No | `PRIMARY KEY` | Identificador único del usuario |
| `nombre_completo` | `VARCHAR(120)` | No | — | Nombre visible |
| `email` | `VARCHAR(120)` | No | `UNIQUE` | Identificador de acceso |
| `rol` | `VARCHAR(30)` | No | `CHECK (rol IN (...))` | Control de acceso RBAC |
| `estado` | `VARCHAR(20)` | No | `DEFAULT 'activo'` | `activo`, `inactivo`, `baja` |
| `eliminado_en` | `TIMESTAMPTZ` | Sí | `NULL` | Soft Delete para preservar auditoría |

*(Repetir para cada tabla o colección del sistema.)*

---

## 3. Vistas, Índices y Consultas Optimizadas

* **Índices críticos:** Listar columnas de búsqueda frecuente, llaves foráneas y filtros compuestos.
* **Vistas / Agregaciones:** Definir vistas calculadas (ej. estados en tiempo real o KPIs del dashboard) para evitar cálculos duplicados en cliente.

---

## 4. Script DDL / Migración Inicial y Seeds

```sql
-- Incluir creación de tablas, constraints CHECK, ON DELETE RESTRICT/CASCADE,
-- índices y datos semilla mínimos (catálogos o configuración inicial).
```

---

## 5. Seguridad a Nivel de Datos (RLS / Políticas de Acceso)

* **Políticas por operación (`SELECT`, `INSERT`, `UPDATE`, `DELETE`):**
  * Detallar qué rol puede leer, crear, modificar o eliminar cada entidad.
* **Integridad contable / histórica:** Especificar qué tablas usan `Soft Delete` o `ON DELETE RESTRICT` para impedir pérdida de trazabilidad.
