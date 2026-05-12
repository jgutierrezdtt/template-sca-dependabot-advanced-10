# Paso 4. Auto merge con condiciones estrictas

## Objetivo de aprendizaje

Automatizar decisiones de revisión, bloqueo o merge sobre PRs de dependencias.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/workflows/dependency-governance.yml`.
- Seccion donde aplicar el cambio: workflow de gobierno de dependencias.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
name: Dependency Governance
on:
  pull_request:
jobs:
  dependency-policy:
    runs-on: ubuntu-latest
    steps:
      - name: Check dependency labels
        run: echo "policy check"
```

## Como adaptarlo correctamente

- Usa un nombre de job que deje claro que gobierna PRs de dependencias.
- Añade condiciones más estrictas para major o paquetes críticos.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-04.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `name: Dependency Governance` en `.github/workflows/dependency-governance.yml`.
- Debe encontrar el marcador `pull_request:` en `.github/workflows/dependency-governance.yml`.
- Debe encontrar el marcador `dependency-policy:` en `.github/workflows/dependency-governance.yml`.
- Debe encontrar el marcador `Check dependency labels` en `.github/workflows/dependency-governance.yml`.

## Criterio de finalizacion

El paso 4 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 5.
