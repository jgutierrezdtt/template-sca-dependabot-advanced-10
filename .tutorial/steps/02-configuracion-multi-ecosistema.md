# Paso 2. Configuracion multi ecosistema

## Objetivo de aprendizaje

Entender que un programa SCA avanzado no debería mirar un solo gestor de paquetes: debe cubrir todas las superficies reales por las que entran dependencias al repositorio.

## Que vas a cambiar y por que

En este paso vas a configurar `.github/dependabot.yml` para varios ecosistemas. La razón es simple: un repositorio moderno puede introducir riesgo desde librerías de aplicación, utilidades internas y también desde imágenes base.

En este template la cobertura mínima pasa por tres ecosistemas distintos:

- `npm` para dependencias JavaScript y tooling asociado
- `pip` para scripts, automatizaciones o utilidades Python
- `docker` para imágenes base y software empaquetado en contenedores

Si dejas uno fuera, la visibilidad del programa SCA queda incompleta aunque el resto esté bien afinado.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Revisa la lista `updates:` y confirma que contiene un bloque por ecosistema relevante.
- Este paso no va de detalle fino todavía; va de asegurar que la cobertura cubre las tres vías principales de entrada de terceros.

## Cambio base recomendado

Usa esta estructura como base para una cobertura multi ecosistema explícita:

```yaml
updates:
  - package-ecosystem: "npm"
    directory: "/"

  - package-ecosystem: "pip"
    directory: "/"

  - package-ecosystem: "docker"
    directory: "/"
```

## Como adaptarlo correctamente

- Mantén un bloque separado por ecosistema; no mezcles lógicas distintas en una sola entrada.
- Ajusta `directory` si el manifiesto no está en la raíz.
- No des por hecho que `docker` es opcional si el repositorio usa imágenes base en su cadena de entrega.
- Si un ecosistema no aplica en un caso real, la excepción debe estar justificada, no omitida por descuido.

## Que deberia verse al terminar

- El archivo deja clara la cobertura sobre `npm`, `pip` y `docker`.
- Otro revisor puede entender que el programa SCA mira varias superficies de riesgo y no solo la principal.
- La configuración parece diseñada para cobertura real, no para cumplir una lista mínima simbólica.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-02.py` comprueba que la cobertura multi ecosistema exista en `.github/dependabot.yml`.
- El workflow busca `package-ecosystem: "npm"` dentro del archivo.
- El workflow busca `package-ecosystem: "pip"` dentro del archivo.
- El workflow busca `package-ecosystem: "docker"` dentro del archivo.

## Criterio de finalizacion

El paso 2 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 3.
