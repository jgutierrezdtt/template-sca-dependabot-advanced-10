# Paso 8. Politica organizativa centralizada

## Objetivo de aprendizaje

Entender que en un escenario avanzado la política de dependencias no debería vivir repartida por equipos o repositorios sin coordinación, sino consolidada en un marco común y centralizado.

## Que vas a cambiar y por que

En este paso vas a trabajar sobre `docs/dependency-policy.md` para que la política no parezca una preferencia local del repositorio, sino una referencia que podría gobernar varios equipos con los mismos criterios de base.

Centralizar la política ayuda a evitar cuatro problemas habituales:

- coberturas distintas según el equipo
- excepciones aprobadas con criterios inconsistentes
- SLA interpretados de forma diferente
- escalados tardíos porque nadie comparte la misma regla

El objetivo es dejar una norma común y entendible, no una colección de notas sueltas.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-policy.md`.
- Revisa las cuatro secciones base que exige el validador.
- Este paso no busca hacer la política más larga, sino más reusable y coherente a nivel organizativo.

## Cambio base recomendado

Usa esta estructura como base para una política centralizada:

```markdown
## Cobertura minima
Define el umbral común de cobertura que deberían cumplir todos los repositorios o equipos afectados.

## Reglas de excepcion
Establece un mecanismo uniforme para aprobar, documentar y revisar excepciones.

## SLA de remediacion
Fija plazos comunes para que la prioridad no cambie arbitrariamente entre equipos.

## Criterios de escalado
Aclara cuándo un caso sale del circuito normal y requiere intervención superior.
```

## Como adaptarlo correctamente

- Escribe la política como norma compartida, no como detalle local del repositorio.
- Evita criterios que dependan demasiado de memoria informal o interpretación personal.
- Asegúrate de que cobertura, excepciones, SLA y escalado sean aplicables de forma homogénea.
- Si el repositorio es plantilla, la política debe enseñar cómo se centraliza una práctica y no solo cómo se documenta una vez.

## Que deberia verse al terminar

- El documento parece una referencia común y no un apunte local.
- Otro revisor puede usarlo para alinear decisiones entre equipos o repositorios.
- La política transmite consistencia organizativa y no solo intención técnica.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-08.py` comprueba que la política exista en `docs/dependency-policy.md`.
- El workflow busca `## Cobertura minima` dentro del archivo.
- El workflow busca `## Reglas de excepcion` dentro del archivo.
- El workflow busca `## SLA de remediacion` dentro del archivo.
- El workflow busca `## Criterios de escalado` dentro del archivo.

## Criterio de finalizacion

El paso 8 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 9.
