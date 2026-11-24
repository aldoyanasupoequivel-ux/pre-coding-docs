# Stack Tecnológico y Arquitectura del Sistema: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Plataforma:** {{Web / PWA / App Móvil / Full-Stack}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Diagrama de Arquitectura de Alto Nivel

```text
┌────────────────────────────────────────────────────────────────────────┐
│                    ARQUITECTURA - {{NOMBRE_PROYECTO}}                  │
└────────────────────────────────────────────────────────────────────────┘

     [ CLIENTE WEB / PWA ]                 [ CLIENTE MÓVIL iOS/Android ]
               │                                         │
               └────────────────────┬────────────────────┘
                                    │ HTTPS / REST / GraphQL / WS
                                    ▼
   ┌──────────────────────────────────────────────────────────────────┐
   │                CAPA DE BACKEND / API / AUTH                      │
   │  • {{Framework / BaaS}}                                          │
   │  • Autenticación y Control de Acceso (RBAC / JWT / RLS)          │
   │  • Reglas de negocio e integraciones externas                    │
   └────────────────────────────────┬─────────────────────────────────┘
                                    │
                                    ▼
   ┌──────────────────────────────────────────────────────────────────┐
   │                 BASE DE DATOS & ALMACENAMIENTO                   │
   │  • {{Motor de BD}}                                               │
   │  • {{Storage / Caché / Offline Store si aplica}}                 │
   └──────────────────────────────────────────────────────────────────┘
```

---

## 2. Selección y Justificación del Stack

| Capa | Tecnología Elegida | Justificación Técnica y de Negocio |
| :--- | :--- | :--- |
| **Frontend / Móvil** | {{Ej. Vite + TypeScript / React / Flutter / React Native}} | {{Rendimiento, mantenibilidad, ecosistema}} |
| **Estilos / UI** | {{Ej. CSS Variables / Tailwind / NativeWind / Material 3}} | {{Consistencia y velocidad de desarrollo}} |
| **Backend / API** | {{Ej. Supabase / Node + Fastify / Python + FastAPI}} | {{Escalabilidad, seguridad, costo}} |
| **Base de Datos** | {{Ej. PostgreSQL / SQLite / Firestore}} | {{Integridad relacional, consultas, offline}} |
| **Hosting / Tiendas** | {{Ej. Vercel / Cloudflare / EAS + App Store & Play Store}} | {{CI/CD, SSL, distribución}} |

---

## 3. Arquitectura de Carpetas (Feature-Based)

```text
{{nombre-repo}}/
├── docs/                          # Documentación pre-código (01 a 12)
├── src/
│   ├── assets/                    # Fuentes, iconos SVG, estilos/tokens base
│   ├── config/                    # Clientes externos, env y configuración
│   ├── core/                      # Componentes compartidos, utilidades, errores
│   ├── modules/                   # Módulos funcionales desacoplados
│   │   ├── auth/
│   │   │   ├── auth.service.*     # Solo acceso a datos / API
│   │   │   └── auth.view.*        # Solo interfaz y eventos
│   │   └── {{modulo_principal}}/
│   │       ├── {{modulo}}.service.*
│   │       └── {{modulo}}.view.*
│   ├── navigation/                # Router web o navigators móviles + guards RBAC
│   └── main.*                     # Punto de entrada
├── tests/                         # Pruebas unitarias, integración y E2E
├── .env.example                   # Plantilla de variables (sin secretos reales)
└── README.md
```

---

## 4. Decisiones de Rendimiento, Offline y Costos

| Requerimiento | Solución Técnica | Costo Estimado Mensual |
| :--- | :--- | :---: |
| **Acceso y distribución** | {{Web HTTPS / PWA / Tiendas móviles}} | {{$0 / monto}} |
| **Persistencia y Auth** | {{Proveedor / Plan}} | {{$0 / monto}} |
| **Modo Offline / Caché** | {{Service Worker / SQLite local / No requerido}} | — |
