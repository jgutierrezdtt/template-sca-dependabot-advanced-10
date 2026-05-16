# Paso 4. Auto merge con condiciones estrictas

## Objetivo de aprendizaje

Entender que el auto-merge solo es aceptable cuando la PR ya ha pasado por un conjunto mínimo de condiciones explícitas y comprobables.


## Por que importa esto

Auto-merge es una de las caracteristicas que mas rapido genera incidentes si se configura sin criterios previos. Una PR que se fusiona automaticamente sin pasar por validaciones puede introducir regresiones, incompatibilidades o incluso dependencias maliciosas si el paquete ha sido comprometido.

La condicion previa no es un obstaculo: es lo que convierte el auto-merge de una decision arriesgada en una herramienta de productividad segura.
## Que vas a cambiar y por que

En este paso vas a trabajar sobre `.github/workflows/dependency-governance.yml` para dejar claro el punto previo a cualquier fusión automática. En un escenario avanzado, el auto-merge no puede basarse en confianza implícita; necesita un workflow que verifique señales mínimas antes de considerar una PR candidata.

En este template, la comprobación de labels representa esa puerta previa:

- la PR entra por `pull_request`
- el job `dependency-policy` aplica la política
- `Check dependency labels` comprueba una condición visible y repetible

La idea importante no es la etiqueta en sí, sino que la automatización solo se apoya en criterios verificables.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/workflows/dependency-governance.yml`.
- Revisa el trigger del workflow y el job que concentra la política de entrada.
- Este paso no te pide activar auto-merge indiscriminado; te pide enseñar qué condiciones estrictas deberían existir antes.

## Cambio base recomendado

Usa esta estructura como referencia para una puerta estricta previa al auto-merge:

```yaml
name: Dependency Governance

on:
  pull_request:

jobs:
  dependency-policy:
    name: Check dependency labels
```


## Que te esta enseñando este cambio

- Las condiciones estrictas antes del auto-merge son la diferencia entre automatizar con criterio y automatizar con riesgo. Las dos configuraciones parecen iguales en el YAML pero tienen consecuencias completamente distintas.
- Limitar el auto-merge a PRs de Dependabot y a tipos `patch` unicamente es la configuracion mas conservadora y mas segura para empezar.
- El concepto de condicion estricta es transferible: el mismo principio aplica a cualquier automatizacion de merge, no solo a dependencias.
- Antes de habilitar auto-merge en produccion, el equipo debe haber validado que los tests automaticos cubren suficiente superficie. Sin tests, el auto-merge acelera la introduccion de errores.
## Como adaptarlo correctamente

- Asegúrate de que el workflow se ejecuta antes de cualquier decisión de fusión.
- Mantén nombres de job y checks alineados con la política que representan.
- No presentes auto-merge como sustituto de análisis; úsalo solo detrás de filtros claros.
- Si una PR no cumple la condición mínima, debe quedarse fuera del camino automático.

## Que deberia verse al terminar

- El repositorio muestra una puerta estricta previa a cualquier automatización de merge.
- Otro revisor puede entender que la política no fusiona PRs de dependencias a ciegas.
- El control parece diseñado para reducir riesgo y no solo para reducir trabajo manual.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-04.py` comprueba que el workflow de gobierno exista en `.github/workflows/dependency-governance.yml`.
- El workflow busca `name: Dependency Governance` dentro del archivo.
- El workflow busca `pull_request:` dentro del archivo.
- El workflow busca `dependency-policy:` dentro del archivo.
- El workflow busca `Check dependency labels` dentro del archivo.

## Criterio de finalizacion

El paso 4 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 5.
