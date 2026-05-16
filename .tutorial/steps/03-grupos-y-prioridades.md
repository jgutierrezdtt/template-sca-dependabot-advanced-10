# Paso 3. Grupos y prioridades

## Objetivo de aprendizaje

Entender como agrupar actualizaciones no rompedoras para reducir ruido operativo sin perder visibilidad sobre cambios que requieren una revisión más cuidadosa.


## Por que importa esto

Un programa SCA sin agrupacion genera una PR por cada actualizacion disponible. En un repositorio con 50 dependencias y cadencia semanal, eso puede ser decenas de PRs simultaneas. El equipo aprende a ignorarlas y el control se vuelve cosmetico.

Los grupos no ocultan informacion: la reorganizan. Agrupar parches y cambios menores juntos reduce el ruido sin perder visibilidad sobre los cambios mayores que merecen revision separada.
## Que vas a cambiar y por que

En este paso vas a usar grupos en `.github/dependabot.yml` para ordenar mejor la cola de PRs. En un repositorio avanzado, recibir una PR por cada parche menor suele saturar la revisión y hace más difícil distinguir lo importante de lo rutinario.

La política del tutorial busca separar:

- cambios `minor` y `patch`, que suelen poder agruparse
- cambios potencialmente rompientes, que conviene mantener fuera del grupo rápido

Así el sistema reduce volumen sin borrar señales de riesgo.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Busca el bloque del ecosistema donde quieres aplicar esta agrupación.
- Este paso no va de auto-merge ni de labels todavía; va de empaquetar con criterio los cambios de bajo impacto relativo.

## Cambio base recomendado

Usa esta estructura como referencia para agrupar actualizaciones no rompedoras:

```yaml
groups:
  non-breaking:
    update-types:
      - minor
      - patch
```


## Que te esta enseñando este cambio

- La prioridad entre grupos no es solo un nombre: define cual se revisa primero cuando hay varias PRs abiertas. Un grupo de `security` con prioridad alta hace que esas PRs suban automaticamente a la cabeza de la cola.
- La separacion entre cambios `minor+patch` y `major` es la distincion mas util en la practica. Los primeros son casi siempre seguros de agrupar; los segundos requieren analisis individual.
- Nombrar los grupos con intencion (`non-breaking`, `security-updates`) comunica la politica directamente en el archivo. Otro revisor entiende el criterio sin documentacion adicional.
- Este patron de grupos es el que usan los equipos con mayor volumen de dependencias para mantener la operacion sostenible sin sacrificar cobertura.
## Como adaptarlo correctamente

- Mantén el grupo dentro del ecosistema correcto.
- Usa un nombre de grupo que haga visible la intención de la política.
- No metas `major` en el mismo grupo si quieres preservar revisión diferenciada para cambios más delicados.
- Si agrupas demasiado sin criterio, reducirás PRs pero también perderás trazabilidad útil.

## Que deberia verse al terminar

- El archivo muestra un grupo `non-breaking` con los tipos `minor` y `patch`.
- Otro revisor entiende que la agrupación busca eficiencia sin ocultar cambios de mayor riesgo.
- La configuración parece diseñada para priorizar, no solo para reducir volumen a cualquier precio.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-03.py` comprueba que la agrupación exista en `.github/dependabot.yml`.
- El workflow busca `groups:` dentro del archivo.
- El workflow busca `non-breaking:` dentro del archivo.
- El workflow busca `update-types:` dentro del archivo.
- El workflow busca `minor` dentro del archivo.
- El workflow busca `patch` dentro del archivo.

## Criterio de finalizacion

El paso 3 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 4.
