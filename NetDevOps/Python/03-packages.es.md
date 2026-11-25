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

## `python -m pip install netmiko`

```bash
python -m pip install netmiko
```

- **Sirve para:** Instalar Netmiko en el entorno Python activo para automatización SSH de dispositivos de red.
- **Parámetros:** `-m pip`: ejecutar pip con el intérprete actual; `install`: instalar desde el índice configurado; `netmiko`: nombre del paquete.
- **Ejemplo de uso:** Dentro de `.venv`, instalar Netmiko para un script de laboratorio que consulte interfaces por SSH.
- **Referencia oficial:** https://pip.pypa.io/en/stable/cli/pip_install/

> Pendiente de validación en laboratorio.

## `python -m pip list`

```bash
python -m pip list
```

- **Sirve para:** Listar paquetes instalados y sus versiones en el entorno activo.
- **Parámetros:** `-m pip`: utilizar el intérprete Python actual; `list`: mostrar distribuciones y versiones instaladas.
- **Ejemplo de uso:** Verificar versiones de Requests y Netmiko antes de ejecutar scripts.
- **Referencia oficial:** https://pip.pypa.io/en/stable/cli/pip_list/

> Pendiente de validación en laboratorio.

## `python -m pip freeze > requirements.txt`

```bash
python -m pip freeze > requirements.txt
```

- **Sirve para:** Exportar las versiones instaladas a un archivo de requisitos para reproducir el laboratorio.
- **Parámetros:** `-m pip freeze`: imprimir paquetes y versiones en formato requirements; `>`: redirección que crea o sobrescribe `requirements.txt`.
- **Ejemplo de uso:** Guardar versiones del `.venv` de un proyecto de integración con NetBox; revisar el archivo antes de versionarlo.
- **Referencia oficial:** https://pip.pypa.io/en/stable/cli/pip_freeze/

> Pendiente de validación en laboratorio.

## `python -m pip install -r requirements.txt`

```bash
python -m pip install -r requirements.txt
```

- **Sirve para:** Instalar las dependencias del proyecto desde un archivo de requisitos revisado en el entorno activo.
- **Parámetros:** `-m pip`: utilizar el intérprete actual; `install`: instalar paquetes; `-r requirements.txt`: leer las dependencias del archivo.
- **Ejemplo de uso:** Recrear dependencias aprobadas en un nuevo `.venv` antes de ejecutar automatización de redes en CI.
- **Referencia oficial:** https://pip.pypa.io/en/stable/cli/pip_install/

> Pendiente de validación en laboratorio.
