# Paso 9. Metricas y reporting operativo

## Objetivo de aprendizaje

Definir qué indicadores sirven para saber si el programa de dependencias mejora o empeora.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-metrics.md`.
- Seccion donde aplicar el cambio: secciones de medicion y tendencia.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```markdown
## Backlog abierto
## Tiempo medio de remediacion
## Excepciones activas
## Tendencia semanal
```

## Como adaptarlo correctamente

- Usa indicadores que puedas revisar en comité de seguridad.
- Evita métricas que no produzcan decisiones operativas.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-09.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `## Backlog abierto` en `docs/dependency-metrics.md`.
- Debe encontrar el marcador `## Tiempo medio de remediacion` en `docs/dependency-metrics.md`.
- Debe encontrar el marcador `## Excepciones activas` en `docs/dependency-metrics.md`.
- Debe encontrar el marcador `## Tendencia semanal` en `docs/dependency-metrics.md`.

## Criterio de finalizacion

El paso 9 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 10.
