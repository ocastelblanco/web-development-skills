---
name: angular-best-practices
description: Guía de mejores prácticas para desarrollo Angular 21+. Usar cuando se necesite crear, revisar, testear o refactorizar componentes, servicios, directivas o aplicaciones Angular. Incluye reglas de arquitectura, rendimiento, seguridad, accesibilidad, manejo de errores, testing con Vitest y tooling. Triggers: "crear componente Angular", "revisar código Angular", "optimizar rendimiento", "refactorizar aplicación", "auditar proyecto Angular".
---

# Angular Best Practices

Skill para garantizar el desarrollo seguro, eficiente y efectivo de aplicaciones Angular 21.1+.

## Cómo Funciona

1. El agente detecta una tarea relacionada con Angular (crear, revisar, refactorizar, testear)
2. Consulta las reglas relevantes en `rules/` según la categoría de la tarea
3. Aplica las reglas durante la implementación o genera un reporte de auditoría
4. Opcionalmente ejecuta scripts de validación automatizada

## Categorías de Reglas

| Categoría | Descripción | Prioridad |
|-----------|-------------|-----------|
| `01-architecture` | Componentes standalone, signals, estructura | Critical |
| `02-performance` | OnPush, lazy loading, bundles, memoización | Critical |
| `03-security` | Sanitización, CSRF, CSP | Critical |
| `04-accessibility` | ARIA, navegación teclado, HTML semántico | High |
| `05-error-handling` | Errores globales, HTTP, flujos reactivos | High |
| `06-testing` | Vitest, cobertura, patrones de test | High |
| `07-tooling` | ESLint, DevTools, optimización de build | Medium |

## Uso

### Auditoría de Proyecto

```bash
node /path/to/skills/angular-best-practices/scripts/audit-angular-project.js [ruta-proyecto]
```

### Verificación de Archivo Específico

```bash
node /path/to/skills/angular-best-practices/scripts/check-best-practices.js [archivo.ts]
```

### Generar Reporte de Cumplimiento

```bash
node /path/to/skills/angular-best-practices/scripts/generate-compliance-report.js [ruta-proyecto]
```

## Niveles de Severidad

- **Critical**: Debe corregirse. Impacta seguridad, rendimiento o funcionalidad.
- **Warning**: Debería corregirse. Viola mejores prácticas establecidas.
- **Suggestion**: Considerar corrección. Mejora calidad o mantenibilidad.

## Integración con Otras Skills

Esta skill complementa `web-design-guidelines` para revisiones completas de UI/UX y accesibilidad. Cuando se audite un componente:

1. Aplicar reglas de `angular-best-practices` para código TypeScript y arquitectura
2. Aplicar reglas de `web-design-guidelines` para templates HTML y estilos

## Reglas por Categoría

### Arquitectura (01-architecture/)
- [001-standalone-components](rules/01-architecture/001-standalone-components.md) - Critical
- [002-signals-pattern](rules/01-architecture/002-signals-pattern.md) - Critical
- [003-component-design](rules/01-architecture/003-component-design.md) - Warning
- [004-file-structure](rules/01-architecture/004-file-structure.md) - Warning
- [005-modern-control-flow](rules/01-architecture/005-modern-control-flow.md) - Critical

### Rendimiento (02-performance/)
- [006-change-detection-onpush](rules/02-performance/006-change-detection-onpush.md) - Critical
- [007-lazy-loading](rules/02-performance/007-lazy-loading.md) - Critical
- [008-optimized-bundles](rules/02-performance/008-optimized-bundles.md) - Critical
- [009-zoneless-angular](rules/02-performance/009-zoneless-angular.md) - Warning
- [010-memoization-patterns](rules/02-performance/010-memoization-patterns.md) - Warning

### Seguridad (03-security/)
- [012-sanitization-requirements](rules/03-security/012-sanitization-requirements.md) - Critical
- [013-csrf-protection](rules/03-security/013-csrf-protection.md) - Critical
- [014-content-security-policy](rules/03-security/014-content-security-policy.md) - Warning

### Accesibilidad (04-accessibility/)
- [015-aria-requirements](rules/04-accessibility/015-aria-requirements.md) - Critical
- [016-keyboard-navigation](rules/04-accessibility/016-keyboard-navigation.md) - Critical
- [017-semantic-html](rules/04-accessibility/017-semantic-html.md) - Warning
- [018-focus-management](rules/04-accessibility/018-focus-management.md) - Warning

### Manejo de Errores (05-error-handling/)
- [019-global-error-handler](rules/05-error-handling/019-global-error-handler.md) - Critical
- [020-http-error-patterns](rules/05-error-handling/020-http-error-patterns.md) - Warning
- [021-reactive-error-flows](rules/05-error-handling/021-reactive-error-flows.md) - Warning

### Testing (06-testing/)
- [022-vitest-setup](rules/06-testing/022-vitest-setup.md) - Critical
- [023-component-testing](rules/06-testing/023-component-testing.md) - Warning
- [024-service-testing](rules/06-testing/024-service-testing.md) - Warning
- [025-coverage-requirements](rules/06-testing/025-coverage-requirements.md) - Warning

### Tooling (07-tooling/)
- [026-eslint-rules](rules/07-tooling/026-eslint-rules.md) - Warning
- [027-angular-devtools](rules/07-tooling/027-angular-devtools.md) - Suggestion
- [028-build-optimizations](rules/07-tooling/028-build-optimizations.md) - Warning

## Templates

Para acelerar el desarrollo, usar los templates en `templates/`:

- `component.template.ts` - Componente standalone con signals
- `service.template.ts` - Servicio con inject() e inyección en root
- `guard.template.ts` - Guard funcional moderno

## Quick Reference

### Componente Mínimo Correcto

```typescript
@Component({
  selector: 'app-example',
  standalone: true,
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `<p>{{ title() }}</p>`
})
export class ExampleComponent {
  readonly title = input.required<string>();
}
```

### Servicio Mínimo Correcto

```typescript
@Injectable({ providedIn: 'root' })
export class ExampleService {
  private readonly http = inject(HttpClient);
}
```
