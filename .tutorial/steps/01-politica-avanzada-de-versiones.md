# Paso 1. Politica avanzada de versiones

## Objetivo de aprendizaje

Entender como definir una politica de versiones avanzada en Dependabot para controlar no solo que se actualiza, sino tambien como se propone cada cambio y que excepciones quedan fuera de la norma general.


## Por que importa esto

Sin una politica de versiones explicita, Dependabot propone cualquier actualizacion que encuentre, incluyendo cambios mayores que pueden romper la aplicacion. Un equipo que no tiene politica acaba aprobando PRs por inercia o rechazandolas por miedo, ninguna de las dos opciones es gobierno.

Una politica avanzada define la norma: que se acepta automaticamente, que requiere revision humana y que queda excluido temporalmente. Con esa base, el equipo puede operar el programa SCA sin depender del conocimiento tacito de cada revisor.
## Que vas a cambiar y por que

En este paso vas a trabajar sobre `.github/dependabot.yml` para fijar una politica de versionado mas consciente. En un escenario avanzado no basta con activar actualizaciones: necesitas decidir la estrategia general y modelar excepciones especificas cuando una dependencia no puede seguirla.

La combinacion de este paso es deliberada:

- `versioning-strategy` expresa la regla base
- `ignore` recoge desvíos concretos
- `dependency-name` obliga a que cada excepción quede acotada a un paquete real

Eso evita dos errores frecuentes: una politica demasiado vaga o una coleccion de excepciones sin criterio comun.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Revisa el bloque del ecosistema donde quieres definir la estrategia avanzada.
- Este paso no va de añadir todos los detalles del archivo, sino de dejar clara la relación entre regla general y excepción puntual.

## Cambio base recomendado

Usa esta estructura como referencia para una politica base con una excepción controlada:

```yaml
versioning-strategy: increase
ignore:
  - dependency-name: "package-with-special-policy"
    versions:
      - ">=3.0.0"
```

Como leerlo:

- `versioning-strategy: increase` fija la política general de propuesta de cambios.
- `ignore` abre el espacio de excepciones justificadas.
- `dependency-name` impide que la excepción quede difusa o demasiado amplia.


## Que te esta enseñando este cambio

- En entornos avanzados, la combinacion de `versioning-strategy` e `ignore` no es una opcion de conveniencia: es la forma de codificar la politica de riesgo del equipo directamente en el archivo de configuracion.
- Una politica sin excepciones no es realista; una politica hecha solo de excepciones no es una politica. La tension entre las dos es lo que este paso quiere que entiendas.
- `versioning-strategy: increase` es la estrategia mas directa: propone la version exacta en lugar de un rango. Es la eleccion correcta cuando quieres control maximo sobre que versiones entran.
- Acotar cada excepcion a un `dependency-name` concreto impide que las exclusiones se conviertan en comodines que silencian el control completo.
## Como adaptarlo correctamente

- Empieza por la estrategia general y usa `ignore` solo para casos concretos.
- Evita una política en la que todo se resuelve a base de exclusiones.
- Si excluyes un rango o una versión, asegúrate de que el motivo sea real y revisable.
- Mantén nombres y restricciones alineados con el ecosistema al que aplican.

## Que deberia verse al terminar

- El archivo deja clara la regla base de actualización.
- Las excepciones aparecen como desviaciones controladas y no como una desactivación encubierta.
- Otro revisor puede entender rápidamente cómo se gobiernan las versiones en este repositorio.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-01.py` comprueba que la politica avanzada exista en `.github/dependabot.yml`.
- El workflow busca `versioning-strategy:` dentro del archivo.
- El workflow busca `ignore:` dentro del archivo.
- El workflow busca `dependency-name:` dentro del archivo.

## Criterio de finalizacion

El paso 1 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 2.
