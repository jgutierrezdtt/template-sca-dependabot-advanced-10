# Paso 7. Quality gate comparado multi-herramienta

## Objetivo

Aplicar el control avanzado de SCA correspondiente para consolidar prácticas de gestión de dependencias en pipeline real.

## Contexto profesional

En programas maduros de AppSec, este control permite escalar la gestión de dependencias con criterio técnico y visibilidad organizativa.

## Explicación técnica

Este paso implementa un quality gate alimentado por la comparación entre `npm audit`, `dependency-check`, `cve-lite-cli` y `osv-scanner`. El gate final debe priorizar hallazgos críticos reproducibles y con remediación clara.

## Archivos que se modifican

- .github/dependabot.yml
- .github/workflows/
- .tutorial/
- docs/

## Acción esperada del usuario

Ejecutar `sca-tool-benchmark.yml`, revisar diferencias entre motores y definir la política de bloqueo (qué severidad y qué motor/es activan fallo de pipeline).

## Validación automática

La validación comprueba que la política de quality gate está definida a partir de evidencia comparada y que el benchmark deja artefactos rastreables.

## Criterio de finalización

El paso queda correctamente aplicado, con resultado reproducible y documentación suficiente para revisión técnica.

## Enlace al siguiente paso

Paso 8.
