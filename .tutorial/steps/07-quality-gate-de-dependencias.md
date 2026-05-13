# Paso 7. Quality gate de dependencias

## Objetivo de aprendizaje

Entender que una PR de dependencias necesita superar un gate previo y visible antes de considerarse lista para revisión o integración.

## Que vas a cambiar y por que

En este paso vas a reforzar `.github/workflows/dependency-governance.yml` como puerta de calidad. En un flujo avanzado, la automatización no solo informa; también decide si una PR cumple condiciones mínimas para entrar en el camino normal.

En este template, el quality gate mínimo se representa con:

- ejecución en `pull_request`
- un job `dependency-policy` dedicado
- una comprobación `Check dependency labels`

Lo importante es la lógica: la PR debe pasar una condición comprobable antes de avanzar.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/workflows/dependency-governance.yml`.
- Revisa el trigger y el job que concentra la política.
- Este paso no va de añadir mucha lógica, sino de dejar claro que existe una puerta previa para cambios de dependencias.

## Cambio base recomendado

Usa esta estructura como referencia para un quality gate mínimo y revisable:

```yaml
name: Dependency Governance

on:
  pull_request:

jobs:
  dependency-policy:
    name: Check dependency labels
```

## Como adaptarlo correctamente

- Formula el gate como una condición observable y no como una intención vaga.
- Mantén el workflow simple y entendible; un gate opaco genera más fricción que valor.
- Si luego añades más criterios, que se entiendan como parte de la misma puerta de entrada.
- Evita mezclar en este archivo comprobaciones ajenas al gobierno de dependencias.

## Que deberia verse al terminar

- El repositorio tiene una puerta de calidad clara para PRs de dependencias.
- Otro revisor puede ver qué condición mínima debe cumplir una PR antes de avanzar.
- El gobierno aparece como control repetible y no como revisión informal.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-07.py` comprueba que el workflow de gobierno exista en `.github/workflows/dependency-governance.yml`.
- El workflow busca `name: Dependency Governance` dentro del archivo.
- El workflow busca `pull_request:` dentro del archivo.
- El workflow busca `dependency-policy:` dentro del archivo.
- El workflow busca `Check dependency labels` dentro del archivo.

## Criterio de finalizacion

El paso 7 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 8.
