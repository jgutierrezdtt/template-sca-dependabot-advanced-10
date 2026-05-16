# Paso 5. Excepciones con trazabilidad completa

## Objetivo de aprendizaje

Entender que una excepción avanzada no solo se registra: debe quedar trazada de forma que cualquier revisor pueda reconstruir qué se aceptó, por qué, quién responde y cuándo debe revisarse.


## Por que importa esto

Una excepcion sin trazabilidad completa es un riesgo sin gobierno. Puede existir en el registro por meses sin que nadie sepa si el motivo sigue siendo valido, quien es responsable de revisarla o cuando debio haberse cerrado.

En auditorias de seguridad, las excepciones son exactamente lo que se revisa con mas cuidado: son las decisiones en las que el equipo eligio no aplicar el control estandar. Si no tienen justificacion, owner y fecha, no son excepciones gobernadas: son omisiones documentadas.
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


## Que te esta enseñando este cambio

- La trazabilidad completa (package + reason + owner + expires_on + status) no es burocracia: es el minimo para que una excepcion sea defendible ante cualquier revision interna o externa.
- Añadir un campo `status` (active, under-review, closed) convierte el registro en algo vivo que puede gestionarse, no solo en un inventario estatico.
- La diferencia entre el nivel profesional y el nivel avanzado es la precision: aqui no basta con que los campos existan, deben contener informacion real que otro revisor puede usar para tomar decisiones.
- Este patron de trazabilidad completa es el estandar en entornos regulados donde las excepciones de seguridad requieren evidencia de revision periodica.
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
