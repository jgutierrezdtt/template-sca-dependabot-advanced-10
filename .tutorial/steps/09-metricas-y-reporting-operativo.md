# Paso 9. Metricas y reporting operativo

## Objetivo de aprendizaje

Entender qué métricas ayudan a operar el programa SCA en el día a día y no solo a presentar estado una vez al mes.


## Por que importa esto

Sin metricas, el estado del programa SCA es una opinion. Con metricas, es un hecho observable. La diferencia importa cuando hay que decidir si invertir mas recursos en el control, si el programa esta mejorando o empeorando, o si alguna decision pasada esta generando deuda acumulada.

Las metricas operativas no son para presentar en un dashboard mensual: son para operar el programa en el dia a dia. Un backlog que crece semana a semana es una señal de alerta antes de que se convierta en un problema visible.
## Que vas a cambiar y por que

En este paso vas a trabajar sobre `docs/dependency-metrics.md` con foco operativo. La idea es que el documento sirva para responder preguntas prácticas: cuánto trabajo queda abierto, cuánto tardas en cerrarlo, cuántas excepciones siguen consumiendo capacidad y si la tendencia semanal mejora o empeora.

Estas métricas no son solo reporting; son señales de gestión:

- `## Backlog abierto` muestra carga pendiente
- `## Tiempo medio de remediacion` muestra velocidad real de cierre
- `## Excepciones activas` muestra deuda aceptada todavía viva
- `## Tendencia semanal` muestra si el sistema converge o se atasca

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependency-metrics.md`.
- Revisa las cuatro secciones base que exige el validador.
- Este paso no va de poner números por ponerlos, sino de dejar un tablero que ayude a decidir dónde actuar primero.

## Cambio base recomendado

Usa esta estructura como base para un seguimiento operativo de deuda:

```markdown
## Backlog abierto
Indica cuántas alertas o PRs de dependencias siguen pendientes y cuál es su volumen relativo.

## Tiempo medio de remediacion
Mide cuánto tarda el equipo en cerrar actualizaciones o vulnerabilidades relevantes.

## Excepciones activas
Cuenta cuántas decisiones de aceptación de riesgo siguen abiertas y qué peso tienen.

## Tendencia semanal
Describe si backlog y excepciones suben, bajan o se mantienen durante la semana.
```


## Que te esta enseñando este cambio

- Backlog, tiempo de remediacion, excepciones activas y tendencia semanal son las cuatro metricas minimas que permiten operar el programa SCA con criterio. Cada una responde una pregunta distinta.
- La tendencia semanal es la metrica mas util a corto plazo: no importa si el backlog es de 5 o de 50, lo que importa es si va subiendo o bajando.
- Separar metricas de reporting ejecutivo de metricas operativas es una decision de audiencia: las metricas de este paso son para el equipo tecnico que opera el programa.
- Este paso enseña que medir un programa de seguridad no es un fin en si mismo: las metricas solo tienen valor si producen decisiones de mejora o detectan degradaciones antes de que sean problemas.
## Como adaptarlo correctamente

- Elige métricas que el equipo pueda actualizar y usar de verdad.
- Evita mezclar todo en un único valor que no permita ver bloqueos o cuellos de botella.
- Relaciona backlog, tiempo de remediación y excepciones para que la lectura tenga contexto.
- Si una tendencia empeora, el documento debería facilitar detectar por qué, no solo señalar el síntoma.

## Que deberia verse al terminar

- El documento sirve para operar el programa SCA y no solo para archivarlo.
- Otro revisor puede detectar si la deuda baja, se estanca o crece.
- Las métricas ayudan a priorizar trabajo y no solo a describirlo.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-09.py` comprueba que el documento de métricas exista en `docs/dependency-metrics.md`.
- El workflow busca `## Backlog abierto` dentro del archivo.
- El workflow busca `## Tiempo medio de remediacion` dentro del archivo.
- El workflow busca `## Excepciones activas` dentro del archivo.
- El workflow busca `## Tendencia semanal` dentro del archivo.

## Criterio de finalizacion

El paso 9 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 10.
