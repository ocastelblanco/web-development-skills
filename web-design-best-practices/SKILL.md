# Web Design Best Practices

## Metadatos

| Campo | Valor |
|-------|-------|
| **Nombre** | web-design-best-practices |
| **Descripcion** | Guia completa de mejores practicas para diseno y desarrollo UI/UX web |
| **Version** | 1.0.0 |
| **Autor** | Basado en Vercel Web Interface Guidelines y comunidad |
| **Idioma** | Espanol |

## Descripcion

Esta skill proporciona una guia exhaustiva de mejores practicas para el diseno y desarrollo de interfaces web modernas. Cubre aspectos fundamentales de UI/UX incluyendo accesibilidad, rendimiento visual, tipografia, formularios, animaciones, responsive design y mas.

## Cuando usar esta skill

Activa esta skill cuando el usuario solicite:

- **Revisar UI/UX**: "revisa mi interfaz", "audita el diseno", "verifica la accesibilidad"
- **Crear componentes**: "crea un formulario", "disena un modal", "implementa un menu"
- **Optimizar diseno**: "mejora la tipografia", "optimiza las animaciones", "corrige el responsive"
- **Implementar modo oscuro**: "agrega dark mode", "implementa temas"
- **Usar Tailwind CSS**: "usa tailwind", "estilos con tailwind", "clases de tailwind"

## Estructura de la Skill

```
web-design-best-practices/
├── SKILL.md                    # Este archivo
├── package.json                # Metadatos del proyecto
├── rules/                      # Reglas organizadas por categoria
│   ├── 01-accesibilidad/       # 10 reglas de accesibilidad
│   ├── 02-focus-estados/       # 6 reglas de focus y estados
│   ├── 03-formularios/         # 11 reglas de formularios
│   ├── 04-animaciones/         # 6 reglas de animacion
│   ├── 05-tipografia/          # 10 reglas de tipografia y contenido
│   ├── 06-imagenes-media/      # 4 reglas de imagenes
│   ├── 07-rendimiento/         # 6 reglas de rendimiento
│   ├── 08-layout-responsive/   # 7 reglas de layout
│   ├── 09-modo-oscuro-temas/   # 4 reglas de temas
│   └── 10-tailwind-css/        # 8 reglas especificas de Tailwind
├── scripts/                    # Scripts de validacion
│   ├── audit-ui-project.js     # Auditoria completa de proyecto
│   ├── check-design-rules.js   # Verificacion de archivo individual
│   └── generate-ui-report.js   # Generador de reportes
└── templates/                  # Plantillas de componentes UI
    ├── button.template.html    # Boton accesible
    ├── form.template.html      # Formulario completo
    ├── modal.template.html     # Modal/Dialog accesible
    ├── card.template.html      # Tarjeta de contenido
    └── navigation.template.html # Menu de navegacion
```

## Categorias de Reglas

### 1. Accesibilidad (01-accesibilidad)
Reglas para garantizar que las interfaces sean usables por todos los usuarios, incluyendo aquellos con discapacidades.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 001-aria-labels.md | Critical | Etiquetas ARIA en botones de icono |
| 002-form-labels.md | Critical | Labels en controles de formulario |
| 003-keyboard-handlers.md | Critical | Manejadores de teclado en elementos interactivos |
| 004-semantic-elements.md | Critical | Uso de elementos semanticos |
| 005-alt-text.md | Critical | Texto alternativo en imagenes |
| 006-decorative-icons.md | Warning | Ocultar iconos decorativos |
| 007-live-regions.md | Warning | Regiones vivas para actualizaciones async |
| 008-semantic-html.md | Critical | HTML semantico antes de ARIA |
| 009-heading-hierarchy.md | Warning | Jerarquia de encabezados |
| 010-skip-links.md | Warning | Enlaces de salto para contenido principal |

### 2. Focus y Estados (02-focus-estados)
Reglas para estados de focus visibles y retroalimentacion de interaccion.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 011-visible-focus.md | Critical | Indicadores de focus visibles |
| 012-focus-replacement.md | Critical | Nunca outline-none sin reemplazo |
| 013-focus-visible.md | Warning | Usar :focus-visible sobre :focus |
| 014-focus-within.md | Suggestion | :focus-within para controles compuestos |
| 015-hover-states.md | Warning | Estados hover en botones y enlaces |
| 016-state-contrast.md | Warning | Jerarquia de contraste en estados |

### 3. Formularios (03-formularios)
Reglas para formularios accesibles, usables y bien disenados.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 017-autocomplete.md | Warning | Autocomplete y name significativos |
| 018-input-types.md | Critical | Tipos de input correctos |
| 019-no-paste-block.md | Critical | Nunca bloquear pegado |
| 020-clickable-labels.md | Warning | Labels clickeables |
| 021-spellcheck.md | Suggestion | Desactivar spellcheck apropiadamente |
| 022-hit-targets.md | Warning | Areas de click en checkbox/radio |
| 023-submit-states.md | Warning | Estados del boton submit |
| 024-error-display.md | Critical | Errores inline junto a campos |
| 025-placeholders.md | Suggestion | Formato de placeholders |
| 026-unsaved-changes.md | Warning | Advertencia de cambios sin guardar |
| 027-validation.md | Warning | Validacion en tiempo real |

### 4. Animaciones (04-animaciones)
Reglas para animaciones performantes y accesibles.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 028-reduced-motion.md | Critical | Respetar prefers-reduced-motion |
| 029-transform-opacity.md | Warning | Solo animar transform/opacity |
| 030-no-transition-all.md | Warning | Nunca transition: all |
| 031-transform-origin.md | Suggestion | Transform-origin correcto |
| 032-svg-transforms.md | Suggestion | Transforms en SVG |
| 033-interruptible.md | Warning | Animaciones interrumpibles |

### 5. Tipografia y Contenido (05-tipografia)
Reglas para tipografia profesional y contenido bien estructurado.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 034-ellipsis.md | Warning | Usar caracter ellipsis real |
| 035-curly-quotes.md | Suggestion | Comillas tipograficas |
| 036-nbsp.md | Warning | Espacios sin ruptura |
| 037-loading-text.md | Suggestion | Texto de estados de carga |
| 038-tabular-nums.md | Warning | Numeros tabulares para columnas |
| 039-text-wrap.md | Suggestion | text-wrap: balance en titulos |
| 040-overflow-text.md | Warning | Manejo de texto largo |
| 041-flex-min-width.md | Warning | min-w-0 en hijos flex |
| 042-empty-states.md | Critical | Manejo de estados vacios |
| 043-copy-guidelines.md | Suggestion | Guias de redaccion |

### 6. Imagenes y Media (06-imagenes-media)
Reglas para imagenes optimizadas y accesibles.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 044-image-dimensions.md | Critical | Dimensiones explicitas |
| 045-lazy-loading.md | Warning | Carga perezosa de imagenes |
| 046-priority-images.md | Warning | Prioridad en imagenes criticas |
| 047-responsive-images.md | Warning | Imagenes responsive |

### 7. Rendimiento (07-rendimiento)
Reglas para interfaces rapidas y eficientes.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 048-virtualization.md | Warning | Virtualizacion de listas largas |
| 049-layout-reads.md | Critical | Evitar lecturas de layout en render |
| 050-dom-batching.md | Warning | Batching de operaciones DOM |
| 051-uncontrolled-inputs.md | Suggestion | Preferir inputs no controlados |
| 052-preconnect.md | Warning | Preconnect a CDNs |
| 053-font-loading.md | Warning | Carga de fuentes criticas |

### 8. Layout y Responsive (08-layout-responsive)
Reglas para layouts flexibles y responsive design.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 054-safe-areas.md | Warning | Safe areas para notches |
| 055-scrollbar-control.md | Warning | Control de scrollbars |
| 056-flex-grid.md | Warning | Flexbox/Grid sobre JS |
| 057-url-state.md | Warning | Estado reflejado en URL |
| 058-touch-action.md | Warning | touch-action: manipulation |
| 059-scroll-behavior.md | Suggestion | overscroll-behavior en modales |
| 060-autofocus.md | Warning | Uso moderado de autofocus |

### 9. Modo Oscuro y Temas (09-modo-oscuro-temas)
Reglas para implementacion correcta de temas.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 061-color-scheme.md | Critical | color-scheme en html |
| 062-theme-color.md | Warning | meta theme-color |
| 063-select-colors.md | Warning | Colores explicitos en select |
| 064-css-variables.md | Warning | Variables CSS para temas |

### 10. Tailwind CSS (10-tailwind-css)
Reglas especificas para proyectos con Tailwind CSS.

| Regla | Severidad | Descripcion |
|-------|-----------|-------------|
| 065-focus-ring.md | Critical | Uso de focus:ring-* |
| 066-dark-variant.md | Warning | Variante dark: consistente |
| 067-responsive-classes.md | Warning | Clases responsive correctas |
| 068-arbitrary-values.md | Suggestion | Uso moderado de valores arbitrarios |
| 069-group-peer.md | Suggestion | Patrones group y peer |
| 070-prose-typography.md | Warning | Plugin typography para contenido |
| 071-container-queries.md | Suggestion | Container queries @container |
| 072-animation-classes.md | Warning | Clases de animacion accesibles |

## Anti-Patrones a Evitar

La skill detecta automaticamente estos anti-patrones criticos:

| Anti-Patron | Problema |
|-------------|----------|
| `user-scalable=no` | Bloquea zoom de accesibilidad |
| `maximum-scale=1` | Bloquea zoom de accesibilidad |
| `onPaste` + `preventDefault` | Bloquea pegado de texto |
| `transition: all` | Transiciones no performantes |
| `outline: none` sin reemplazo | Elimina indicadores de focus |
| `<div onClick>` para navegacion | No semantico, sin soporte de teclado |
| `<div>` o `<span>` como botones | No semantico, no accesible |
| Imagenes sin dimensiones | Causa CLS (layout shift) |
| Listas largas sin virtualizar | Problemas de rendimiento |
| Inputs sin labels | No accesible |
| Botones de icono sin aria-label | No accesible |
| Formatos de fecha/numero hardcodeados | Problemas de i18n |

## Uso de Scripts

### Auditoria completa de proyecto

```bash
node scripts/audit-ui-project.js ./mi-proyecto-web
```

Analiza todos los archivos HTML, CSS, JS/TS y genera un reporte completo.

### Verificacion de archivo individual

```bash
node scripts/check-design-rules.js src/components/Button.tsx
```

Verifica un archivo especifico contra todas las reglas.

### Generacion de reportes

```bash
# Reporte en terminal (default)
node scripts/generate-ui-report.js src/

# Reporte JSON para CI/CD
node scripts/generate-ui-report.js src/ --json > report.json

# Reporte HTML visual
node scripts/generate-ui-report.js src/ --html > report.html
```

## Compatibilidad

| Herramienta | Soporte |
|-------------|---------|
| Claude Code | Si |
| Cursor | Si |
| GitHub Copilot | Si |
| Codeium | Si |

## Skills Complementarias

Esta skill se integra bien con:

- `angular-best-practices-21`: Para proyectos Angular
- `react-best-practices`: Para proyectos React/Next.js
- `vue-best-practices`: Para proyectos Vue

## Recursos Externos

- [Vercel Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [MDN Web Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
