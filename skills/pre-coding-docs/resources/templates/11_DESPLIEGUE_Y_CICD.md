# Guía Operativa de Despliegue y CI/CD: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Plataforma:** {{Web / PWA / App Móvil iOS & Android}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Arquitectura de Despliegue

```text
[ Desarrollador ] ──► [ GitHub (PR -> main) ] ──► [ Pipeline CI (Lint + Tests + Build) ]
                                                                │
                              ┌─────────────────────────────────┴─────────────────────────────────┐
                              ▼                                                                   ▼
                 [ Web / API Hosting (CD) ]                                        [ Tiendas Móviles (si aplica) ]
                 ({{Vercel / Cloudflare / Cloud}})                                 (TestFlight / Play Console / EAS)
```

---

## 2. Entornos y Flujo CI/CD

| Entorno | Rama / Trigger | Propósito | URL / Canal |
| :--- | :--- | :--- | :--- |
| **Local** | Rama `feat/*` | Desarrollo y pruebas unitarias | `localhost` / Emulador |
| **Preview / Staging** | Pull Request | Validación visual y QA antes de merge | URL temporal / TestFlight / Internal Track |
| **Producción** | Merge a `main` / Tag `vX.Y.Z` | Usuarios finales (Zero-Downtime) | `{{URL_PRODUCCION}}` / Tiendas |

---

## 3. Variables de Entorno (`.env.example`)

> **Seguridad:** Nunca documentes claves reales aquí. Configura los valores secretos únicamente en el gestor de secretos del proveedor de CI/CD o hosting.

| Variable | Entorno | Descripción | Ejemplo / Placeholder |
| :--- | :---: | :--- | :--- |
| `{{APP_API_URL}}` | Todos | URL base de la API / BaaS | `https://api.ejemplo.com` |
| `{{APP_PUBLIC_KEY}}` | Todos | Clave pública de cliente | `{{PUBLIC_KEY_PLACEHOLDER}}` |

---

## 4. Distribución e Instalación

* **Si es Web / PWA:** configuración de HTTPS automático, dominio personalizado (DNS) e instrucciones de instalación en escritorio/móvil.
* **Si es App Móvil:** estrategia de versionado semántico (`versionName` / `versionCode` / `CFBundleVersion`), firma de certificados y flujo de revisión en App Store / Google Play.

---

## 5. Matriz de Costos Operativos

| Componente | Proveedor | Plan | Costo Mensual Estimado |
| :--- | :--- | :--- | :---: |
| **Hosting / CDN** | {{Proveedor}} | {{Plan}} | {{$0 / monto}} |
| **Base de Datos / Auth** | {{Proveedor}} | {{Plan}} | {{$0 / monto}} |
| **CI/CD / Tiendas** | {{GitHub / Apple / Google}} | {{Plan}} | {{$0 / cuota anual}} |
| **Total Estimado** | — | — | **{{Total}}** |
