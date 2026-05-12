# Paso 3. Grupos y prioridades

## Objetivo de aprendizaje

Este paso introduce un control de SCA y debe dejar un cambio comprensible en .github/dependabot.yml.

## Que vas a cambiar y por que

Actualiza .github/dependabot.yml para que el control de "grupos y prioridades" quede explícito y revisable.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
groups:
non-breaking:
update-types:
minor
patch
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
- `scripts/validate-step-03.py` comprueba este paso contra el archivo configurado.
- El workflow busca `groups:` dentro de `.github/dependabot.yml`.
- El workflow busca `non-breaking:` dentro de `.github/dependabot.yml`.
- El workflow busca `update-types:` dentro de `.github/dependabot.yml`.
- El workflow busca `minor` dentro de `.github/dependabot.yml`.
- El workflow busca `patch` dentro de `.github/dependabot.yml`.

## Criterio de finalizacion

El paso 3 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 4.
