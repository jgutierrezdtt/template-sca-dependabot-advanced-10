# Paso 3. Grupos y prioridades

## Objetivo de aprendizaje

Agrupar actualizaciones similares para reducir ruido y revisar cambios de forma más eficiente.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Seccion donde aplicar el cambio: bloque groups de Dependabot.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
groups:
  non-breaking:
    patterns:
      - "*"
    update-types:
      - "minor"
      - "patch"
```

## Como adaptarlo correctamente

- Usa un grupo para cambios no disruptivos.
- Separa major si quieres exigir revisión más estricta.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-03.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `groups:` en `.github/dependabot.yml`.
- Debe encontrar el marcador `non-breaking:` en `.github/dependabot.yml`.
- Debe encontrar el marcador `update-types:` en `.github/dependabot.yml`.
- Debe encontrar el marcador `minor` en `.github/dependabot.yml`.
- Debe encontrar el marcador `patch` en `.github/dependabot.yml`.

## Criterio de finalizacion

El paso 3 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 4.
