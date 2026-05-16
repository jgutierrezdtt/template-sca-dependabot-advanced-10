# Paso 10. Medalla final sca advanced

## Objetivo de aprendizaje

Cerrar el tutorial con una comprobación final de madurez que resuma los controles esenciales del recorrido advanced.


## Por que importa esto

Cerrar el tutorial con una comprobacion de madurez no es solo un ejercicio de validacion: es el momento de consolidar la vision completa de lo que has construido y entender como se relacionan los distintos controles entre si.

Un programa SCA avanzado no es la suma de 10 configuraciones independientes. Es un sistema donde la politica de versiones, las excepciones, el quality gate y las metricas se refuerzan mutuamente.
## Que vas a cambiar y por que

En este paso vas a completar `docs/sca-checklist.md` para convertirlo en una verificación final del estado del repositorio. No se trata solo de marcar casillas: la checklist debe dejar claro si el sistema tiene cobertura automatizada, gobierno de PRs, excepciones trazables y visibilidad operativa suficiente.

Este cierre importa porque un programa SCA maduro no depende de una sola pieza. Necesita que varias capacidades trabajen juntas:

- detección continua con Dependabot
- gobierno explícito sobre PRs de dependencias
- excepciones registradas y revisables
- reporting suficiente para seguir la operación

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/sca-checklist.md`.
- Mantén las cuatro secciones base que exige el validador.
- Haz que la checklist se lea como una validación final del nivel alcanzado, no como texto genérico.

## Cambio base recomendado

Usa esta estructura como base para el cierre del tutorial:

```markdown
## Dependabot activo
Confirma que la detección y actualización automatizada de dependencias está habilitada.

## Gobierno de PRs activo
Verifica que las PRs de dependencias pasan por controles y condiciones explícitas.

## Excepciones documentadas
Comprueba que los riesgos aceptados quedan registrados con responsable y vencimiento.

## Reporting disponible
Confirma que el equipo puede medir backlog, remediación y tendencia operativa.
```


## Que te esta enseñando este cambio

- La comprobacion final del checklist verifica que los cuatro pilares del programa SCA estan operativos: Dependabot activo, gobierno de PRs, excepciones documentadas y reporting disponible. Ninguno de los cuatro es suficiente por si solo.
- Un programa que tiene Dependabot activo pero sin gobierno de PRs genera alertas sin proceso de cierre. Un programa con excepciones documentadas pero sin revision periodica acumula riesgo sin saberlo.
- El nivel advanced no significa mas reglas: significa mayor precision, mayor trazabilidad y mayor capacidad de operar el programa a escala.
- Lo que has construido en estos 10 pasos es la base tecnica de un programa SCA profesional. El siguiente nivel es integrarlo con herramientas SBOM, escaneado de licencias y deteccion de dependencias maliciosas.
## Como adaptarlo correctamente

- Usa cada sección como un criterio verificable, no como un titular vacío.
- Evita repetir el contenido exacto de pasos anteriores; aquí toca resumir el estado final alcanzado.
- Si algo depende de otro documento o workflow, deja clara esa relación.
- La checklist debe servir para una revisión rápida de madurez antes de dar el template por bueno.

## Que deberia verse al terminar

- El repositorio queda con una definición clara de lo que significa completar el nivel advanced.
- Otro revisor puede usar la checklist para comprobar si faltan capacidades importantes.
- El cierre del tutorial conecta automatización, gobierno, excepciones y reporting en una sola vista.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-10.py` comprueba que la checklist final exista en `docs/sca-checklist.md`.
- El workflow busca `## Dependabot activo` dentro del archivo.
- El workflow busca `## Gobierno de PRs activo` dentro del archivo.
- El workflow busca `## Excepciones documentadas` dentro del archivo.
- El workflow busca `## Reporting disponible` dentro del archivo.

## Criterio de finalizacion

El paso 10 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Este es el ultimo paso del tutorial.
