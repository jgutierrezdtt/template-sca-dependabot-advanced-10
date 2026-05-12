# Paso 10. Medalla final sca advanced

## Objetivo de aprendizaje

Cerrar el itinerario con una evidencia clara de qué controles quedan operativos.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/sca-checklist.md`.
- Seccion donde aplicar el cambio: checklist final.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```markdown
## Dependabot activo
## Gobierno de PRs activo
## Excepciones documentadas
## Reporting disponible
```

## Como adaptarlo correctamente

- Marca solo controles realmente implantados.
- Usa este documento como resumen final del recorrido.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-10.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `## Dependabot activo` en `docs/sca-checklist.md`.
- Debe encontrar el marcador `## Gobierno de PRs activo` en `docs/sca-checklist.md`.
- Debe encontrar el marcador `## Excepciones documentadas` en `docs/sca-checklist.md`.
- Debe encontrar el marcador `## Reporting disponible` en `docs/sca-checklist.md`.

## Criterio de finalizacion

El paso 10 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Este es el ultimo paso del tutorial.
