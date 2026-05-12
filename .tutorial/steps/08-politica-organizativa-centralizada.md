# Paso 8. Politica organizativa centralizada

## Objetivo de aprendizaje

Documentar las reglas de operación para que el control sea consistente entre repositorios.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-policy.md`.
- Seccion donde aplicar el cambio: norma organizativa para dependencias.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```markdown
## Cobertura minima
## Reglas de excepcion
## SLA de remediacion
## Criterios de escalado
```

## Como adaptarlo correctamente

- Conecta la política con el workflow y los labels usados en el repositorio.
- Especifica qué pasa cuando un paquete crítico no se puede actualizar.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-08.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `## Cobertura minima` en `docs/dependency-policy.md`.
- Debe encontrar el marcador `## Reglas de excepcion` en `docs/dependency-policy.md`.
- Debe encontrar el marcador `## SLA de remediacion` en `docs/dependency-policy.md`.
- Debe encontrar el marcador `## Criterios de escalado` en `docs/dependency-policy.md`.

## Criterio de finalizacion

El paso 8 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 9.
