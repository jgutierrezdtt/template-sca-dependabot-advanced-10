# Paso 1. Politica avanzada de versiones

## Objetivo de aprendizaje

Controlar qué actualizaciones se aceptan automáticamente y cuáles deben esperar.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Seccion donde aplicar el cambio: bloques ignore y allow/versioning-strategy.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
versioning-strategy: increase
ignore:
  - dependency-name: "example-lib"
    update-types:
      - "version-update:semver-major"
```

## Como adaptarlo correctamente

- Usa ignore solo cuando tengas una razón técnica documentada.
- Evita ignorar categorías enteras sin revisión periódica.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-01.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `versioning-strategy:` en `.github/dependabot.yml`.
- Debe encontrar el marcador `ignore:` en `.github/dependabot.yml`.
- Debe encontrar el marcador `dependency-name:` en `.github/dependabot.yml`.

## Criterio de finalizacion

El paso 1 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 2.
