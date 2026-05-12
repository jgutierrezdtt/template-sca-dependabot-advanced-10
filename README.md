# SCA Dependabot Advanced 10

Tutorial avanzado y compacto de gestión de dependencias con Dependabot en 10 pasos clave.

## Objetivo

Aplicar un conjunto seleccionado de prácticas avanzadas de SCA con Dependabot: configuración por ecosistema, política de versiones, excepciones trazables, auto-merge controlado, quality gates y métricas operativas.

## Audiencia

Equipos de AppSec y DevSecOps con experiencia previa en Dependabot que quieran consolidar prácticas avanzadas en formato compacto.

## Requisitos previos

- Haber completado el tutorial SCA Dependabot Professional o tener experiencia equivalente.
- Conocimientos sólidos de GitHub Actions.
- Experiencia gestionando dependencias y alertas de seguridad.

## Herramientas utilizadas

- GitHub Dependabot
- GitHub Actions
- GitHub Security Advisories
- Scripts de validación del curso

## Inicio del tutorial

[![Empezar tutorial](https://img.shields.io/badge/Empezar%20tutorial-0b69ff?style=for-the-badge&logo=github&logoColor=white)](../../actions/workflows/start.yml)

## Acceso al repositorio

- [Crear mi repositorio desde este template](https://github.com/new?template_name=template-sca-dependabot-advanced-10&template_owner=jgutierrezdtt)
- [Volver al portal general](https://github.com/jgutierrezdtt/security-learning-portal)

## Gestión del progreso

- [Validar progreso](../../actions/workflows/validate.yml)
- [Probar integridad del tutorial](../../actions/workflows/test-tutorial.yml)
- [Ejecutar tests funcionales del tutorial](../../actions/workflows/functional-tests.yml)
- [Reiniciar tutorial](../../actions/workflows/reset-tutorial.yml)
- [Ver pasos del tutorial](./.tutorial/steps/)

## Arquitectura del laboratorio

El laboratorio condensa los 10 controles avanzados más relevantes de Dependabot en un flujo operativo completo, desde política avanzada de versiones hasta auto-merge, quality gates y reporting con métricas.

## Tabla de pasos

| Paso | Tema |
| --- | --- |
| 0 | Introducción |
| 1 | Política avanzada de versiones |
| 2 | Configuración multi-ecosistema |
| 3 | Grupos y prioridades |
| 4 | Auto-merge con condiciones estrictas |
| 5 | Excepciones con trazabilidad completa |
| 6 | Transitividad y análisis de impacto |
| 7 | Quality gate de dependencias |
| 8 | Política organizativa centralizada |
| 9 | Métricas y reporting operativo |
| 10 | Medalla final SCA Advanced |

## Paso 0

El paso 0 describe el entorno, permisos y limitaciones del laboratorio. No bloquea el flujo: el botón principal abre directamente el paso 1.

## Actualización desde template

Este repositorio incluye `.template-version` y workflow de actualización para revisar cambios del template sin sobrescribir trabajo del usuario.

## Badge final

Al cerrar el curso se generan artefactos de finalización en:

- `.tutorial/badges/completion-badge.md`
- `.tutorial/badges/completion-badge.svg`
- `.tutorial/evidence/completion.json`

## Referencias

- [Dependabot documentation](https://docs.github.com/code-security/dependabot)
- [GitHub Security Advisories](https://github.com/advisories)
- [GitHub Actions](https://docs.github.com/actions)
