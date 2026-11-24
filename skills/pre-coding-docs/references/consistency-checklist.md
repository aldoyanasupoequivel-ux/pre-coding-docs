# Checklist de Auditoría Cruzada Pre-Código

Ejecuta esta verificación antes de dar por cerrada la documentación de `docs/`:

## 1. Coherencia de Negocio y Roles (RBAC)
- [ ] Todos los roles definidos en `01_GUION_OPERATIVO.md` coinciden exactamente en nombre y permisos con la matriz de `02_ARQUITECTURA_VISTAS.md` y las políticas de seguridad de `06_MODELO_BASE_DE_DATOS.md`.
- [ ] Las exclusiones explícitas del MVP en `01_GUION_OPERATIVO.md` no fueron introducidas por accidente en `03_HISTORIAS_DE_USUARIO.md` ni en `06_MODELO_BASE_DE_DATOS.md`.

## 2. Trazabilidad de Requisitos y Sprints
- [ ] Cada flujo crítico de `01_GUION_OPERATIVO.md` está cubierto por al menos una Historia de Usuario (`HU-XX`) en `03_HISTORIAS_DE_USUARIO.md`.
- [ ] Todas las Historias de Usuario tienen criterios de aceptación en formato BDD/Gherkin (`Dado que / Cuando / Entonces`).
- [ ] El 100% de las HUs `Must Have` están asignadas a un Sprint en `04_PLANIFICACION_SPRINTS.md` y los totales de Story Points cuadran.

## 3. Coherencia Técnica y de Datos
- [ ] Todas las pantallas y acciones descritas en `02_ARQUITECTURA_VISTAS.md` tienen respaldo de entidades/campos en `06_MODELO_BASE_DE_DATOS.md` y endpoints/servicios en `09_CONTRATOS_API_INTEGRACIONES.md`.
- [ ] Si es una **App Móvil**, se definieron explícitamente: navegación nativa (TabBar/Stack/Drawer), permisos del dispositivo, estrategia offline/caché y distribución en tiendas.
- [ ] Si es **Web / PWA**, se definieron explícitamente: diseño responsive, estrategia de enrutamiento y despliegue HTTPS.
- [ ] Los nombres de módulos en la estructura de carpetas (`05_STACK_Y_ARQUITECTURA.md`) coinciden con las convenciones de `08_INDICACIONES_TECNICAS.md`.

## 4. Seguridad, Calidad y Operación
- [ ] No existe ninguna clave API real, contraseña, token ni URL privada sensible en ningún `.md` (solo placeholders).
- [ ] Los criterios de aceptación críticos de `03_HISTORIAS_DE_USUARIO.md` tienen pruebas mapeadas en `10_ESTRATEGIA_TESTING_QA.md`.
- [ ] `11_DESPLIEGUE_Y_CICD.md` y `12_BACKUPS_Y_MIGRACION.md` son consistentes con el stack y proveedor elegido en `05_STACK_Y_ARQUITECTURA.md`.
