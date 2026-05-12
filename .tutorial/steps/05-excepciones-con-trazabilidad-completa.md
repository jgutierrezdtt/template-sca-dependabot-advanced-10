# Paso 5. Excepciones con trazabilidad completa

## Objetivo de aprendizaje

En este paso vas a practicar un control de SCA para entender que decision de configuracion aplicar y por que.

## Que debe hacer la persona participante

1. Revisar el contexto del control en este paso.
2. Editar la configuracion esperada en `.github/dependabot.yml`.
3. Guardar y subir el cambio en el flujo normal del repositorio (commit/push o PR).

## Que configurar exactamente

- Campo o seccion objetivo: relacionado con "Excepciones con trazabilidad completa".
- Ubicacion principal: `.github/dependabot.yml`.
- Resultado esperado: que la configuracion refleje el control del paso 5.

## Checklist de configuracion

- El cambio del paso 5 esta presente en `.github/dependabot.yml`.
- El cambio es coherente con el objetivo del paso.
- El repositorio incluye la evidencia de progreso para este paso.

## Validacion automatica (sin ejecucion manual)

- `validate-steps.yml` se ejecuta automaticamente por eventos `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-05.py` valida que el control de este paso esta aplicado.
- El estado de progreso se refleja en `.tutorial/state.json`.

## Criterio de finalizacion

El paso 5 se marca como completado cuando GitHub Actions reporta exito para `validate-step-05.py`.

Siguiente paso: Paso 6.
