# Paso 9. Metricas y reporting operativo

## Objetivo de aprendizaje

Este paso introduce un control de SCA y debe dejar un cambio comprensible en docs/dependency-metrics.md.

## Que vas a cambiar y por que

Actualiza docs/dependency-metrics.md para que el control de "metricas y reporting operativo" quede explícito y revisable.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-metrics.md`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```markdown
## Backlog abierto
## Tiempo medio de remediacion
## Excepciones activas
## Tendencia semanal
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
- `scripts/validate-step-09.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Backlog abierto` dentro de `docs/dependency-metrics.md`.
- El workflow busca `## Tiempo medio de remediacion` dentro de `docs/dependency-metrics.md`.
- El workflow busca `## Excepciones activas` dentro de `docs/dependency-metrics.md`.
- El workflow busca `## Tendencia semanal` dentro de `docs/dependency-metrics.md`.

## Criterio de finalizacion

El paso 9 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 10.
