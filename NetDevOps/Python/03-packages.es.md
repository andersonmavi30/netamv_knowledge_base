---
tags: [python, netdevops, automation, cli]
validation: not-lab-verified
---

# pip y dependencias del proyecto

[🇬🇧 English](03-packages.md) · [🇨🇴 Español](03-packages.es.md) · [↩ Python](README.es.md)

**Plataforma:** Python 3.10+; Linux/macOS Bash; en Windows los comandos de activación son diferentes.

## `python -m pip install requests`

```bash
python -m pip install requests
```

- **Sirve para:** Instalar el cliente HTTP `requests` en el entorno Python activo para automatizar APIs REST.
- **Parámetros:** `-m pip`: ejecutar pip con el intérprete activo; `install`: descargar/instalar; `requests`: nombre del paquete. Requiere acceso al índice.
- **Ejemplo de uso:** Instalar Requests dentro de `.venv` para consultar una API REST de NetBox o firewall en laboratorio; revisar y fijar versiones aprobadas.
- **Referencia oficial:** https://pip.pypa.io/en/stable/cli/pip_install/

> Pendiente de validación en laboratorio.
