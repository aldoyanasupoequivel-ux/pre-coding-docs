# Guía de Estilo y Sistema de Diseño Visual: {{NOMBRE_PROYECTO}}

**Proyecto:** {{NOMBRE_PROYECTO}}  
**Plataforma:** {{Web / PWA / App Móvil}}  
**Versión:** 1.0  
**Fecha:** {{FECHA}}  

---

## 1. Identidad de Marca y Activos

| Activo | Ruta en el Proyecto | Formato | Uso Principal |
| :--- | :--- | :---: | :--- |
| **Logotipo** | `{{src/assets/logo.svg}}` | SVG | Cabecera, Login, Splash |
| **Isotipo / App Icon** | `{{public/favicon.svg / assets/icon.png}}` | SVG / PNG | Favicon, PWA, Icono iOS/Android |

---

## 2. Paleta de Colores (Regla 60 - 30 - 10)

* **60% Dominante (Fondo / Canvas):** `{{HEX}}` — {{Propósito visual}}
* **30% Secundario (Superficies, tarjetas, barras, bordes):** `{{HEX}}` / Borde `{{HEX}}`
* **10% Acento (Marca y CTAs primarios):** `{{HEX}}` (texto sobre acento: `{{HEX}}`)

### Colores Semánticos de Estado

| Estado | Significado en el Sistema | Color Texto/Borde | Color Fondo Sutil |
| :--- | :--- | :---: | :---: |
| **Éxito / Activo** | {{Estado positivo}} | `#22C55E` | `rgba(34, 197, 94, 0.12)` |
| **Advertencia** | {{Estado preventivo}} | `#F59E0B` | `rgba(245, 158, 11, 0.12)` |
| **Error / Bloqueo** | {{Estado crítico}} | `#EF4444` | `rgba(239, 68, 68, 0.12)` |
| **Info / Neutro** | {{Estado informativo}} | `#3B82F6` | `rgba(59, 130, 246, 0.12)` |

---

## 3. Tipografía

1. **Display / Títulos / KPIs:** `{{Familia 1}}` — Pesos `{{700, 800}}`
2. **Cuerpo / Tablas / Formularios:** `{{Familia 2}}` — Pesos `{{400, 500, 600}}`

---

## 4. Design Tokens (CSS Variables / Theme Móvil)

```css
/* Adaptar a theme.ts / ThemeData si es React Native o Flutter */
:root {
  --bg-app: {{HEX}};
  --surface-card: {{HEX}};
  --border-subtle: {{HEX}};
  --brand-primary: {{HEX}};
  --brand-on-primary: {{HEX}};
  --text-main: {{HEX}};
  --text-muted: {{HEX}};
  --radius-sm: 6px;
  --radius-md: 10px;
  --radius-lg: 14px;
}
```

---

## 5. Especificaciones de Componentes Clave

* **Botones:** Primario, Secundario, Peligro y Deshabilitado (estados `hover`, `active`, `loading`, `disabled`).
* **Inputs y Selects:** Borde de foco visible, etiqueta clara, estado de error con mensaje inline.
* **Componente Crítico del Negocio:** {{Describir la tarjeta, tabla o vista estrella de la app}}.

---

## 6. Accesibilidad y Ergonomía (Web y Móvil)

1. **Contraste WCAG AA:** mínimo `4.5:1` en texto normal y `3:1` en texto grande / iconos.
2. **Área táctil mínima:** `44x44px` (Web/iOS) o `48x48dp` (Android) en todos los controles interactivos.
3. **Iconografía:** Solo iconos vectoriales limpios (SVG / Lucide / SF Symbols / Material Symbols). Cero emojis en la interfaz.
4. **Feedback no intrusivo:** Estados visuales claros, skeletons de carga y mensajes de error accionables.
