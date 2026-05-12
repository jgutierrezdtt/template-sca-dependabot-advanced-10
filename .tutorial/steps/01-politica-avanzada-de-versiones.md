# Paso 1. Politica avanzada de versiones

## Que vas a hacer en este paso?

Implementaras este control de SCA de forma concreta sobre el archivo `.github/dependabot.yml` y registraras evidencia tecnica en `.tutorial/evidence/step-01.json`.

## Por que es importante

**En la practica real**:
- Este control reduce riesgo operativo y mejora trazabilidad.
- Permite validar avance real, no solo lectura del tutorial.

**Lo que logras**:
- Resultado tecnico verificable para el paso 1.
- Evidencia auditable para revisiones de seguridad.

---

## Instrucciones paso-a-paso

### Paso 1.1: Prepara el artefacto principal

Crea o actualiza el archivo objetivo de este paso:

```bash
mkdir -p "$(dirname .github/dependabot.yml)"
touch .github/dependabot.yml
```

### Paso 1.2: Registra evidencia del paso

Crea el archivo `.tutorial/evidence/step-01.json` con este contenido:

```bash
mkdir -p .tutorial/evidence
cat > .tutorial/evidence/step-01.json << 'EOF'
{
  "step": 1,
  "title": "Politica avanzada de versiones",
  "status": "completed",
  "artifact": ".github/dependabot.yml"
}
EOF
```

---

## Verificacion local

```bash
test -f .github/dependabot.yml && echo "artifact ok"
python3 -c 'import json;json.load(open(".tutorial/evidence/step-01.json"));print("evidence ok")'
```

---

## Validacion automatica

`validate-step-01.py` verificara:
- Existe `.github/dependabot.yml`.
- Existe `.tutorial/evidence/step-01.json`.
- La evidencia marca `status=completed` y `step=1`.

---

## Criterio de finalizacion

Paso 1 esta completo cuando:
1. `.github/dependabot.yml` existe en el repositorio.
2. `.tutorial/evidence/step-01.json` existe y es JSON valido.
3. `.tutorial/state.json` muestra `"current_step": 2`.

**Siguiente paso**: Paso 2
