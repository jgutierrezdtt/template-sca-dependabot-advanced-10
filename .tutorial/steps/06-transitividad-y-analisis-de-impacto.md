# Paso 6. Transitividad y analisis de impacto

## Objetivo de aprendizaje

Entender que el impacto real de una vulnerabilidad cambia cuando la dependencia es transitiva y cuando su scope limita o amplifica la exposición del sistema.


## Por que importa esto

La mayoria de las vulnerabilidades de supply chain entran por dependencias transitivas, no directas. Si el equipo solo mira el manifiesto principal, puede creer que esta protegido cuando en realidad tiene vectores de entrada que no ve.

Entender la transitividad no es un detalle tecnico: es lo que separa un analisis de impacto real de una lectura superficial de alertas. Un paquete vulnerable que llega como transitivo puede tener una ruta de remediacion completamente distinta a uno que controlas directamente.
## Que vas a cambiar y por que

En este paso vas a reforzar `docs/dependabot-triage.md` para que el análisis no se quede en el nombre del paquete vulnerable. En escenarios avanzados necesitas responder dos preguntas adicionales:

- ¿la dependencia es directa o llega arrastrada por otra?
- ¿el scope y el contexto de uso hacen que el impacto sea mayor o menor?

Eso cambia la decisión final porque también cambia tu capacidad de remediación. A veces no puedes actualizar el paquete afectado directamente; tienes que mover una dependencia padre o aceptar una mitigación temporal.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dependabot-triage.md`.
- Mantén las cuatro secciones base del documento.
- Refuerza sobre todo `## Paquete afectado`, `## Impacto en negocio` y `## Decision` con la información de transitividad y alcance.

## Cambio base recomendado

Usa esta estructura como base para un triage con contexto suficiente:

```markdown
## Paquete afectado
Indica si la dependencia es directa o transitiva y desde qué paquete principal llega.

## Severidad tecnica
Resume la vulnerabilidad y su severidad.

## Impacto en negocio
Explica si el scope es de producción, desarrollo, build o test y qué cambia eso en el riesgo.

## Decision
Aclara si puedes corregir directamente o si dependes de una actualización en cadena.
```


## Que te esta enseñando este cambio

- El analisis de impacto en el contexto de dependencias transitivas requiere responder tres preguntas: quien arrastra el paquete vulnerable, en que scope llega y puedo corregirlo directamente o debo esperar al paquete padre.
- Documentar esas tres respuestas en el informe de triage es lo que convierte una alerta en un plan de remediacion accionable.
- El scope (produccion, desarrollo, test) no cambia si la vulnerabilidad existe: cambia la urgencia de corregirla y el riesgo de no hacerlo.
- Este paso enseña que la profundidad del analisis es lo que diferencia un programa SCA avanzado de uno que simplemente responde a alertas sin entender el contexto.
## Como adaptarlo correctamente

- No trates una dependencia transitiva como si estuviera bajo control directo si no lo está.
- No ignores una transitive solo porque no aparezca en el manifiesto principal.
- Explica el scope con precisión; runtime y tooling no implican el mismo nivel de urgencia.
- Haz que la decisión final refleje tanto exposición como capacidad real de corrección.

## Que deberia verse al terminar

- El documento deja claro cómo llega la dependencia vulnerable al proyecto.
- Otro revisor puede entender si el impacto está en runtime o en un scope más acotado.
- La decisión final parece apoyada en exposición y remediación real, no solo en la CVE.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-06.py` comprueba que el documento de triage conserve sus cuatro secciones base en `docs/dependabot-triage.md`.
- El workflow busca `## Paquete afectado` dentro del archivo.
- El workflow busca `## Severidad tecnica` dentro del archivo.
- El workflow busca `## Impacto en negocio` dentro del archivo.
- El workflow busca `## Decision` dentro del archivo.

## Criterio de finalizacion

El paso 6 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 7.
