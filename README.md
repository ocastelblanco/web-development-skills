# Web Development Skills

Repositorio de **skills** para Claude Code y otros agentes de IA, siguiendo el [protocolo oficial de Claude Code Skills](https://code.claude.com/docs/en/skills) y el estándar abierto [Agent Skills](https://agentskills.io).

## Descripción

Este repositorio contiene skills modulares y reutilizables que los agentes de IA pueden utilizar para:

- Aplicar mejores prácticas automáticamente al generar código
- Auditar proyectos existentes en busca de problemas
- Proporcionar sugerencias contextuales y específicas del framework
- Generar código que sigue estándares de la industria

## Skills Disponibles

### 1. Angular Best Practices (`angular-best-practices`)

Mejores prácticas para **Angular 21.1.x** y versiones posteriores.

| Caracteristica | Descripción |
|----------------|-------------|
| **Reglas** | 27 reglas organizadas en 7 categorías |
| **Scripts** | 3 scripts de validación y auditoría |
| **Plantillas** | Componentes, servicios y guards |

**Categorías:** Arquitectura, Rendimiento, Seguridad, Accesibilidad, Manejo de Errores, Testing, Tooling

```bash
# Auditar proyecto
node angular-best-practices-21/scripts/audit-angular-project.js ./mi-app

# Verificar archivo
node angular-best-practices-21/scripts/check-best-practices.js src/app/app.component.ts

# Generar reporte HTML
node angular-best-practices-21/scripts/generate-compliance-report.js src/app --html > reporte.html
```

---

### 2. Angular Firebase Authentication (`angular-firebase`)

Implementación de autenticación Firebase en **Angular 21.1.x** usando AngularFire y patrones modernos.

| Caracteristica | Descripción |
|----------------|-------------|
| **Métodos** | Email/Password, Proveedores Sociales, Teléfono, Anónimo |
| **Referencias** | 6 guías detalladas |
| **Plantillas** | Servicios, componentes login/registro, guards |

**Métodos soportados:** Email/Password, Google, Facebook, Twitter, Autenticación por teléfono, Login anónimo

```bash
# Usar templates para crear servicio de auth
# Usar guards para proteger rutas
# Usar patrones reactivos con Signals
```

---

### 3. Web Design Best Practices (`web-design-best-practices`)

Mejores prácticas de **diseño UI/UX web**, basada en [Vercel Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines).

| Caracteristica | Descripción |
|----------------|-------------|
| **Reglas** | 24+ reglas organizadas en 10 categorías |
| **Scripts** | 3 scripts de validación y auditoría |
| **Plantillas** | Botones, Formularios, Modales, Cards, Navegación |

**Categorías:** Accesibilidad, Focus/Estados, Formularios, Animaciones, Tipografía, Imágenes, Rendimiento, Layout, Modo Oscuro, Tailwind CSS

```bash
# Auditar proyecto
node web-design-best-practices/scripts/audit-ui-project.js ./mi-proyecto

# Verificar archivo
node web-design-best-practices/scripts/check-design-rules.js src/components/Button.tsx

# Generar reporte HTML
node web-design-best-practices/scripts/generate-ui-report.js src/ --html > reporte.html
```

---

## Instalación en Claude Code

Las skills siguen el [protocolo oficial de Claude Code](https://code.claude.com/docs/en/skills) y pueden instalarse de tres formas:

### Opción 1: Skills Personales (todos tus proyectos)

```bash
# Copiar a ~/.claude/skills/
cp -r angular-best-practices-21 ~/.claude/skills/angular-best-practices
cp -r angular-firebase/angular-firebase-authentication ~/.claude/skills/angular-firebase-authentication
cp -r web-design-best-practices ~/.claude/skills/web-design-best-practices
```

### Opción 2: Skills de Proyecto (solo este proyecto)

```bash
# Copiar a .claude/skills/ en tu proyecto
mkdir -p .claude/skills
cp -r angular-best-practices-21 .claude/skills/angular-best-practices
cp -r angular-firebase/angular-firebase-authentication .claude/skills/angular-firebase-authentication
cp -r web-design-best-practices .claude/skills/web-design-best-practices
```

### Opcion 3: Como Plugin

Agregar este repositorio como submodulo o dependencia y referenciar las skills.

## Uso

Una vez instaladas, las skills se activan automáticamente cuando Claude detecta contexto relevante, o puedes invocarlas directamente:

```
/angular-best-practices
/angular-firebase-authentication
/web-design-best-practices
```

Claude usará las instrucciones del skill y podrá consultar los archivos de referencias, templates y scripts según sea necesario.

## Estructura del Repositorio

```
web-development-skills/
├── README.md
├── angular-best-practices-21/
│   ├── SKILL.md              # Instrucciones principales (frontmatter YAML)
│   ├── package.json
│   ├── rules/                # Reglas detalladas por categoría
│   ├── scripts/              # Scripts de auditoría
│   └── templates/            # Plantillas de código
│
├── angular-firebase/
│   └── angular-firebase-authentication/
│       ├── SKILL.md              # Instrucciones principales (frontmatter YAML)
│       ├── references/           # Guías detalladas por método de auth
│       └── templates/            # Plantillas de servicios y componentes
│
└── web-design-best-practices/
    ├── SKILL.md              # Instrucciones principales (frontmatter YAML)
    ├── package.json
    ├── rules/                # Reglas detalladas por categoría
    ├── scripts/              # Scripts de auditoría
    └── templates/            # Plantillas de componentes UI
```

## Formato SKILL.md

Cada skill tiene un `SKILL.md` con frontmatter YAML según el protocolo de Claude Code:

```yaml
---
name: nombre-del-skill
description: Descripción para que Claude sepa cuándo usar el skill
allowed-tools: Read, Grep, Glob, Bash(node *)
---

# Instrucciones concisas para Claude

## Reglas principales
- Regla 1
- Regla 2

## Recursos adicionales
- [Categoría](rules/categoria/) - Descripción
```

### Campos del Frontmatter

| Campo | Requerido | Descripción |
|-------|-----------|-------------|
| `name` | No | Nombre del skill (default: nombre del directorio) |
| `description` | Recomendado | Cuándo usar el skill |
| `allowed-tools` | No | Herramientas permitidas sin confirmación |
| `disable-model-invocation` | No | Si `true`, solo el usuario puede invocarlo |
| `user-invocable` | No | Si `false`, no aparece en menú `/` |
| `context` | No | `fork` para ejecutar en subagente aislado |

## Formato de Reglas

Cada regla en `rules/` sigue este formato:

```markdown
# [ID]: [Nombre de la Regla]

## Metadatos
| Campo | Valor |
|-------|-------|
| **ID** | Identificador único |
| **Severidad** | Critical / Warning / Suggestion |
| **Categoría** | Categoría |

## Descripción
Explicación de la regla

## Anti-Patrón (Incorrecto)
Ejemplo de código a evitar

## Patrón Correcto
Ejemplo de código correcto

## Detección Automática
Patrones regex o lógica

## Referencias
Enlaces a documentación
```

## Severidad de Reglas

| Nivel | Descripción |
|-------|-------------|
| **Critical** | Debe corregirse (seguridad, accesibilidad grave) |
| **Warning** | Debería corregirse (mejores prácticas) |
| **Suggestion** | Considerar corrección (calidad) |

## Compatibilidad

| Herramienta | Soporte |
|-------------|---------|
| Claude Code | Completo (protocolo oficial) |
| Cursor | Completo |
| GitHub Copilot | Parcial |
| Otros agentes | Parcial (estandar Agent Skills) |

## Fuentes y Créditos

- [Claude Code Skills Protocol](https://code.claude.com/docs/en/skills)
- [Agent Skills Standard](https://agentskills.io)
- [Vercel Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines)
- [Angular Official Documentation](https://angular.dev)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)

## Contribuir

1. Seguir la estructura de carpetas existente
2. Crear `SKILL.md` con frontmatter YAML válido
3. Incluir reglas detalladas en `rules/`
4. Agregar scripts de validación en `scripts/`
5. Documentar en español

## Licencia

MIT License

---

Desarrollado con la asistencia de Claude (Anthropic) para la comunidad de desarrollo web.
