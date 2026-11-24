# Guía de Backups, Continuidad y Migración: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Proveedor Principal:** {{Ej. Supabase / AWS / Neon / Firebase}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Límites del Proveedor y Riesgos Conocidos

Documenta los límites reales del plan contratado (almacenamiento, ancho de banda, pausas por inactividad, retención de backups) y su mitigación:

| Riesgo / Límite del Plan | Impacto en el Negocio | Mitigación Definida |
| :--- | :--- | :--- |
| **{{Ej. Pausa por inactividad / Cuota de filas}}** | {{Bajo / Medio / Alto}} | {{Monitoreo, alertas o upgrade planificado}} |
| **{{Ej. Sin backups automáticos en capa gratuita}}** | {{Alto}} | {{Respaldo manual/programado semanal externo}} |

---

## 2. Procedimiento de Backup y Restauración

### Frecuencia y Retención
* **Frecuencia:** {{Diaria / Semanal / Antes de cada migración de esquema}}.
* **Almacenamiento seguro:** {{Carpeta cifrada en nube externa / repositorio seguro fuera del proveedor principal}}.

### Comandos / Herramientas de Respaldo
```bash
# Ejemplo PostgreSQL (reemplazar placeholders antes de ejecutar)
pg_dump -h {{DB_HOST}} -U {{DB_USER}} -d {{DB_NAME}} > backup_{{PROYECTO}}_YYYYMMDD.sql
```

### Prueba de Restauración
* Verificar periódicamente que el archivo de respaldo restaura correctamente en un entorno local o staging.

---

## 3. Matriz de Portabilidad y Plan de Migración

| Componente | ¿Dependencia fuerte del proveedor? | Estrategia de Migración |
| :--- | :---: | :--- |
| **Frontend / App Móvil** | No | Cambiar únicamente variables de entorno / adaptador de servicio |
| **Lógica de Negocio** | No | Encapsulada en `src/modules/*` |
| **Esquema y Datos** | {{No / Parcial}} | Exportación estándar (`SQL` / `JSON` / `CSV`) + importación en destino |
| **Autenticación** | {{Parcial}} | Exportar usuarios o migrar tokens/proveedores OAuth |

### Alternativas de Destino Pre-Evaluadas
1. **Alternativa Cloud:** {{Ej. Neon / Render / Railway / RDS}} — tiempo estimado de corte: {{X horas}}.
2. **Alternativa Local / Self-Hosted:** {{Ej. Docker + PostgreSQL + VPN privada}} — tiempo estimado: {{X horas}}.
