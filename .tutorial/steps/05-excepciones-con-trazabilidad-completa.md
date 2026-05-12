# Paso 5. Excepciones con trazabilidad completa

## Objetivo de aprendizaje

Registrar las excepciones para que sean temporales, auditables y comprensibles.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-exceptions.yml`.
- Seccion donde aplicar el cambio: lista de excepciones con trazabilidad.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
exceptions:
  - package: "example-lib"
    reason: "bloqueo temporal por compatibilidad"
    owner: "team-security"
    expires_on: "2026-12-31"
```

## Como adaptarlo correctamente

- Cada excepción debe tener una fecha de caducidad.
- No aceptes excepciones sin responsable claro.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-05.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `exceptions:` en `docs/dependency-exceptions.yml`.
- Debe encontrar el marcador `package:` en `docs/dependency-exceptions.yml`.
- Debe encontrar el marcador `reason:` en `docs/dependency-exceptions.yml`.
- Debe encontrar el marcador `owner:` en `docs/dependency-exceptions.yml`.
- Debe encontrar el marcador `expires_on:` en `docs/dependency-exceptions.yml`.

## Criterio de finalizacion

El paso 5 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 6.
