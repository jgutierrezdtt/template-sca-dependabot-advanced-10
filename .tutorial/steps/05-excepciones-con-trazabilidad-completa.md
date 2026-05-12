# Paso 5. Excepciones con trazabilidad completa

## Objetivo de aprendizaje

Este paso introduce un control de SCA y debe dejar un cambio comprensible en docs/dependency-exceptions.yml.

## Que vas a cambiar y por que

Actualiza docs/dependency-exceptions.yml para que el control de "excepciones con trazabilidad completa" quede explícito y revisable.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-exceptions.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
exceptions:
package:
reason:
owner:
expires_on:
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
- `scripts/validate-step-05.py` comprueba este paso contra el archivo configurado.
- El workflow busca `exceptions:` dentro de `docs/dependency-exceptions.yml`.
- El workflow busca `package:` dentro de `docs/dependency-exceptions.yml`.
- El workflow busca `reason:` dentro de `docs/dependency-exceptions.yml`.
- El workflow busca `owner:` dentro de `docs/dependency-exceptions.yml`.
- El workflow busca `expires_on:` dentro de `docs/dependency-exceptions.yml`.

## Criterio de finalizacion

El paso 5 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 6.
