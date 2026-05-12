# Paso 6. Transitividad y analisis de impacto

## Objetivo de aprendizaje

Documentar como analizar una alerta, valorar su impacto y decidir su tratamiento.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependabot-triage.md`.
- Seccion donde aplicar el cambio: documento de triaje y decision.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```markdown
## Paquete afectado
## Severidad tecnica
## Impacto en negocio
## Decision
- actualizar
- aplazar
- excepcion temporal
```

## Como adaptarlo correctamente

- Incluye un ejemplo real de paquete vulnerable.
- Explica por que se actualiza o se difiere el cambio.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-06.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `## Paquete afectado` en `docs/dependabot-triage.md`.
- Debe encontrar el marcador `## Severidad tecnica` en `docs/dependabot-triage.md`.
- Debe encontrar el marcador `## Impacto en negocio` en `docs/dependabot-triage.md`.
- Debe encontrar el marcador `## Decision` en `docs/dependabot-triage.md`.

## Criterio de finalizacion

El paso 6 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 7.
