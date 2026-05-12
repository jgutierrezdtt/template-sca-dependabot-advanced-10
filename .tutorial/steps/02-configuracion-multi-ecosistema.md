# Paso 2. Configuracion multi ecosistema

## Objetivo de aprendizaje

Extender la cobertura a varios ecosistemas con una estructura clara y mantenible.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/dependabot.yml`.
- Seccion donde aplicar el cambio: lista updates con un bloque por ecosistema.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
- package-ecosystem: "npm"
  directory: "/"
  schedule:
    interval: "weekly"
- package-ecosystem: "pip"
  directory: "/"
  schedule:
    interval: "weekly"
- package-ecosystem: "docker"
  directory: "/"
  schedule:
    interval: "weekly"
```

## Como adaptarlo correctamente

- Añade mas ecosistemas solo si realmente existen en tu repositorio.
- No mezcles varios directorios distintos en un mismo bloque si el manifiesto cambia de ruta.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-02.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `package-ecosystem: "npm"` en `.github/dependabot.yml`.
- Debe encontrar el marcador `package-ecosystem: "pip"` en `.github/dependabot.yml`.
- Debe encontrar el marcador `package-ecosystem: "docker"` en `.github/dependabot.yml`.

## Criterio de finalizacion

El paso 2 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 3.
