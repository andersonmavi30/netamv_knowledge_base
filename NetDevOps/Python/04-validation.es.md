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

## `python -m json.tool payload.json`

```bash
python -m json.tool payload.json
```

- **Sirve para:** Validar la sintaxis JSON y mostrar un archivo formateado en la terminal.
- **Parámetros:** `-m json.tool`: ejecutar la utilidad JSON estándar; `payload.json`: archivo de entrada de ejemplo. JSON inválido genera error y salida distinta de cero.
- **Ejemplo de uso:** Comprobar el cuerpo JSON de una solicitud API de NetBox o firewall antes de ejecutarla.
- **Referencia oficial:** https://docs.python.org/3/library/json.html#module-json.tool

> Pendiente de validación en laboratorio.
