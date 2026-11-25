---
tags: [python, netdevops, automation, cli]
validation: not-lab-verified
---

# Entornos virtuales

[🇬🇧 English](02-virtual-environments.md) · [🇨🇴 Español](02-virtual-environments.es.md) · [↩ Python](README.es.md)

**Plataforma:** Python 3.10+; Linux/macOS Bash; en Windows los comandos de activación son diferentes.

## `python3 -m venv .venv`

```bash
python3 -m venv .venv
```

- **Sirve para:** Crear un entorno Python aislado en el directorio `.venv` del proyecto.
- **Parámetros:** `-m venv`: ejecutar el módulo estándar de entornos virtuales; `.venv`: carpeta que se crea. Requiere `venv`.
- **Ejemplo de uso:** Antes de integrar la API de NetBox, crear un entorno aislado para las dependencias del proyecto.
- **Referencia oficial:** https://docs.python.org/3/library/venv.html

> Pendiente de validación en laboratorio.
