---
tags: [python, netdevops, automation, cli]
validation: not-lab-verified
---

# Validación y diagnóstico

[🇬🇧 English](04-validation.md) · [🇨🇴 Español](04-validation.es.md) · [↩ Python](README.es.md)

**Plataforma:** Python 3.10+; entorno virtual recomendado.

## `python -m pip check`

```bash
python -m pip check
```

- **Sirve para:** Comprobar dependencias declaradas que falten o presenten incompatibilidades.
- **Parámetros:** `-m pip`: utilizar el intérprete activo; `check`: reportar conflictos de dependencias; solo consulta.
- **Ejemplo de uso:** Detectar incompatibilidades de dependencias en el entorno virtual del proyecto.
- **Referencia oficial:** https://pip.pypa.io/en/stable/cli/pip_check/

> Pendiente de validación en laboratorio.
