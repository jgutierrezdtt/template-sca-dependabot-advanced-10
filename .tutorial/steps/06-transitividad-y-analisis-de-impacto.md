# Paso 6. Transitividad y analisis de impacto

## Objetivo de aprendizaje

Este paso introduce un control de SCA y debe dejar un cambio comprensible en docs/dependabot-triage.md.

## Que vas a cambiar y por que

Actualiza docs/dependabot-triage.md para que el control de "transitividad y analisis de impacto" quede explícito y revisable.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependabot-triage.md`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```markdown
## Paquete afectado
## Severidad tecnica
## Impacto en negocio
## Decision
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa nombres claros para secciones, reglas o jobs.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-06.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Paquete afectado` dentro de `docs/dependabot-triage.md`.
- El workflow busca `## Severidad tecnica` dentro de `docs/dependabot-triage.md`.
- El workflow busca `## Impacto en negocio` dentro de `docs/dependabot-triage.md`.
- El workflow busca `## Decision` dentro de `docs/dependabot-triage.md`.

## Criterio de finalizacion

El paso 6 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 7.
