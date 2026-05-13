# Paso 5. Excepciones con trazabilidad completa

## Objetivo de aprendizaje

Entender que una excepción avanzada no solo se registra: debe quedar trazada de forma que cualquier revisor pueda reconstruir qué se aceptó, por qué, quién responde y cuándo debe revisarse.

## Que vas a cambiar y por que

En este paso vas a trabajar sobre `docs/dependency-exceptions.yml` para que cada excepción sea auditables y no una nota ambigua. La trazabilidad completa es lo que permite distinguir entre una excepción controlada y una deuda que simplemente se escondió en un archivo.

Una excepción con trazabilidad completa deja visibles al menos estas piezas:

- el paquete afectado
- el motivo técnico u operativo
- el owner responsable
- la fecha de caducidad o revisión

Sin una de ellas, la excepción pierde contexto y se vuelve más difícil de revisar o cerrar correctamente.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-exceptions.yml`.
- Revisa la lista `exceptions:` y completa cada entrada como un caso independiente.
- Este paso no va de acumular excepciones, sino de garantizar que cada una tenga información suficiente para gobernarse.

## Cambio base recomendado

Usa esta estructura como referencia para una excepción con trazabilidad completa:

```yaml
exceptions:
  - package: "lodash"
    reason: "La actualización propuesta rompe una integración todavía no migrada"
    owner: "team-platform"
    expires_on: "2026-07-31"
```

## Como adaptarlo correctamente

- Describe el motivo con suficiente detalle como para que otro equipo pueda entenderlo sin buscar una PR antigua.
- Usa un owner real que pueda responder por la decisión.
- No dejes `expires_on` como campo testimonial; debe implicar revisión futura.
- Separa excepciones distintas en entradas distintas para no mezclar justificaciones.

## Que deberia verse al terminar

- El archivo actúa como registro de decisiones y no como una lista opaca de exclusiones.
- Otro revisor puede reconstruir el contexto de cada excepción sin información adicional.
- La deuda queda documentada con suficiente precisión para ser auditada y cerrada después.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-05.py` comprueba que el registro de excepciones exista en `docs/dependency-exceptions.yml`.
- El workflow busca `exceptions:` dentro del archivo.
- El workflow busca `package:` dentro del archivo.
- El workflow busca `reason:` dentro del archivo.
- El workflow busca `owner:` dentro del archivo.
- El workflow busca `expires_on:` dentro del archivo.

## Criterio de finalizacion

El paso 5 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 6.
