# Contratos de API e Integraciones Externas: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Estilo de Comunicación:** {{REST JSON / GraphQL / SDK BaaS (Supabase/Firebase) / WebSockets}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Convenciones Generales

* **URL Base:** `{{API_BASE_URL}}` (configurada por variable de entorno).
* **Autenticación:** `{{Bearer JWT / Session Cookie / API Key}}`.
* **Formato de Fechas y Moneda:** ISO-8601 (`YYYY-MM-DDTHH:mm:ssZ`), montos numéricos con 2 decimales.
* **Formato Estándar de Error:**
```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Descripción clara para el cliente",
    "details": []
  }
}
```

---

## 2. Catálogo de Endpoints / Operaciones de Servicio

| Módulo | Método / Operación | Ruta / RPC | Rol Permitido | Descripción |
| :--- | :---: | :--- | :--- | :--- |
| **Auth** | `POST` | `/auth/login` | Público | Autentica y retorna sesión/rol |
| **{{Módulo}}** | `GET` | `/{{recurso}}` | `{{Rol}}` | Lista paginada con filtros |
| **{{Módulo}}** | `POST` | `/{{recurso}}` | `{{Rol}}` | Crea nuevo registro |

### Detalle de Payloads Críticos

#### `POST /{{recurso}}`
* **Request:**
```json
{
  "campo_1": "valor",
  "campo_2": 100.00
}
```
* **Response (`201 Created`):**
```json
{
  "id": "uuid",
  "estado": "activo",
  "creado_en": "2026-01-01T12:00:00Z"
}
```
* **Códigos de error esperados:** `400` (validación), `401` (no autenticado), `403` (sin permiso), `409` (duplicado).

---

## 3. Integraciones con Servicios de Terceros

| Servicio Externo | Propósito | Método de Integración | Manejo de Fallos / Fallback |
| :--- | :--- | :--- | :--- |
| **{{Ej. WhatsApp / Email}}** | {{Notificaciones / Bienvenida}} | {{Deep link `wa.me` / API REST}} | {{Reintento o mensaje manual}} |
| **{{Ej. Pasarela de Pago / Push}}** | {{Cobros / Alertas móviles}} | {{SDK + Webhook}} | {{Idempotencia y cola de reintento}} |
