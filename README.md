# Web Development Skills

Repositorio de **skills** para agentes de IA orientados al desarrollo web. Estas skills proporcionan reglas, mejores practicas, scripts de validacion y plantillas para asistentes de codigo como Claude Code, Cursor, GitHub Copilot y otros.

## Descripcion

Este repositorio contiene conjuntos de skills modulares y reutilizables que los agentes de IA pueden utilizar para:

- Aplicar mejores practicas automaticamente al generar codigo
- Auditar proyectos existentes en busca de problemas
- Proporcionar sugerencias contextuales y especificas del framework
- Generar codigo que sigue estandares de la industria

## Skills Disponibles

### 1. Angular Best Practices 21 (`angular-best-practices-21`)

Guia completa de mejores practicas para **Angular 21.1.x** y versiones posteriores.

| Caracteristica | Descripcion |
|----------------|-------------|
| **Reglas** | 27 reglas organizadas en 7 categorias |
| **Scripts** | 3 scripts de validacion y auditoria |
| **Plantillas** | Componentes, servicios y guards |
| **Severidad** | Critical, Warning, Suggestion |

**Categorias:**
- Arquitectura (Standalone, Signals, Control Flow moderno)
- Rendimiento (OnPush, Lazy Loading, Zoneless)
- Seguridad (Sanitizacion, CSRF, CSP)
- Accesibilidad (ARIA, Teclado, Semantica)
- Manejo de Errores
- Testing (Vitest)
- Tooling (ESLint, DevTools)

```bash
# Auditar un proyecto Angular
node angular-best-practices-21/scripts/audit-angular-project.js ./mi-app

# Verificar un archivo especifico
node angular-best-practices-21/scripts/check-best-practices.js src/app/app.component.ts

# Generar reporte de cumplimiento
node angular-best-practices-21/scripts/generate-compliance-report.js src/app --html > reporte.html
```

---

### 2. Web Design Best Practices (`web-design-best-practices`)

Guia completa de mejores practicas para **diseno y desarrollo UI/UX web**, basada en las [Vercel Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines) y otras fuentes de la comunidad.

| Caracteristica | Descripcion |
|----------------|-------------|
| **Reglas** | 72+ reglas organizadas en 10 categorias |
| **Scripts** | 3 scripts de validacion y auditoria |
| **Plantillas** | Botones, Formularios, Modales, Cards, Navegacion |
| **Tailwind CSS** | Reglas especificas para Tailwind |

**Categorias:**
- Accesibilidad (ARIA, Labels, Teclado, Semantica, Skip Links)
- Focus y Estados (Indicadores visibles, :focus-visible)
- Formularios (Autocomplete, Validacion, Errores inline)
- Animaciones (prefers-reduced-motion, transform/opacity)
- Tipografia (Ellipsis, Numeros tabulares, Text wrap)
- Imagenes y Media (Dimensiones, Lazy loading)
- Rendimiento (Virtualizacion, Layout reads)
- Layout y Responsive (Safe areas, Scrollbars)
- Modo Oscuro y Temas (color-scheme, CSS variables)
- Tailwind CSS (focus:ring, dark: variant)

```bash
# Auditar un proyecto web
node web-design-best-practices/scripts/audit-ui-project.js ./mi-proyecto

# Verificar un archivo especifico
node web-design-best-practices/scripts/check-design-rules.js src/components/Button.tsx

# Generar reporte de cumplimiento
node web-design-best-practices/scripts/generate-ui-report.js src/ --html > reporte.html
```

---

## Estructura del Repositorio

```
web-development-skills/
├── README.md                           # Este archivo
├── angular-best-practices-21/          # Skill de Angular 21+
│   ├── SKILL.md                        # Documentacion del skill
│   ├── package.json                    # Metadatos
│   ├── rules/                          # 27 reglas en 7 categorias
│   ├── scripts/                        # 3 scripts de validacion
│   └── templates/                      # Plantillas de componentes
│
└── web-design-best-practices/          # Skill de UI/UX Web
    ├── SKILL.md                        # Documentacion del skill
    ├── package.json                    # Metadatos
    ├── rules/                          # 72+ reglas en 10 categorias
    │   ├── 01-accesibilidad/
    │   ├── 02-focus-estados/
    │   ├── 03-formularios/
    │   ├── 04-animaciones/
    │   ├── 05-tipografia/
    │   ├── 06-imagenes-media/
    │   ├── 07-rendimiento/
    │   ├── 08-layout-responsive/
    │   ├── 09-modo-oscuro-temas/
    │   └── 10-tailwind-css/
    ├── scripts/                        # 3 scripts de validacion
    └── templates/                      # 5 plantillas de componentes UI
```

## Uso con Agentes de IA

### Claude Code

```bash
# Agregar skills al contexto de Claude Code
claude --skill ./web-development-skills/angular-best-practices-21
claude --skill ./web-development-skills/web-design-best-practices
```

### Cursor

Las skills pueden ser agregadas como reglas personalizadas en la configuracion de Cursor.

### GitHub Copilot

Incluir los archivos `SKILL.md` en el contexto del proyecto para que Copilot los considere.

## Formato de Reglas

Cada regla sigue un formato estandar:

```markdown
# [ID]: [Nombre de la Regla]

## Metadatos
| Campo | Valor |
|-------|-------|
| **ID** | [Identificador unico] |
| **Severidad** | Critical / Warning / Suggestion |
| **Categoria** | [Categoria] |

## Descripcion
[Explicacion de la regla]

## Anti-Patron (Incorrecto)
[Ejemplo de codigo a evitar]

## Patron Correcto
[Ejemplo de codigo correcto]

## Deteccion Automatica
[Patrones regex o logica para detectar violaciones]

## Referencias
[Enlaces a documentacion oficial]
```

## Severidad de Reglas

| Nivel | Descripcion | Accion |
|-------|-------------|--------|
| **Critical** | Problemas de seguridad, accesibilidad grave, o errores | Debe corregirse |
| **Warning** | Mejores practicas no seguidas | Deberia corregirse |
| **Suggestion** | Mejoras opcionales de calidad | Considerar correccion |

## Scripts de Validacion

Todos los skills incluyen tres tipos de scripts:

### 1. Auditoria de Proyecto
Escanea todo el proyecto y genera un reporte completo.

```bash
node scripts/audit-*.js ./ruta-proyecto
```

### 2. Verificacion de Archivo
Analiza un archivo individual contra todas las reglas.

```bash
node scripts/check-*.js archivo.tsx
```

### 3. Generacion de Reportes
Genera reportes en multiples formatos (terminal, JSON, HTML).

```bash
node scripts/generate-*-report.js ./src --json > reporte.json
node scripts/generate-*-report.js ./src --html > reporte.html
```

## Compatibilidad

| Herramienta | Soporte |
|-------------|---------|
| Claude Code | Completo |
| Cursor | Completo |
| GitHub Copilot | Completo |
| Codeium | Completo |
| Otros agentes | Parcial* |

*Las skills usan formato Markdown estandar que puede ser interpretado por la mayoria de agentes.

## Fuentes y Creditos

Este repositorio se basa en y adapta contenido de:

- [Vercel Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines)
- [VoltAgent Awesome Agent Skills](https://github.com/VoltAgent/awesome-agent-skills)
- [Vercel Labs Agent Skills](https://github.com/vercel-labs/agent-skills)
- [Angular Official Documentation](https://angular.dev)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)

## Contribuir

Las contribuciones son bienvenidas. Para agregar una nueva skill o regla:

1. Seguir la estructura de carpetas existente
2. Usar el formato de reglas estandar
3. Incluir ejemplos de codigo correctos e incorrectos
4. Agregar patrones de deteccion automatica
5. Actualizar el SKILL.md y package.json correspondiente

## Licencia

MIT License - Ver archivo LICENSE para mas detalles.

---

Desarrollado con la asistencia de Claude (Anthropic) para la comunidad de desarrollo web.
