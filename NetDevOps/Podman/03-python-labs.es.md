---
tags: [podman, containers, netdevops, cli, python]
validation: not-lab-verified
---

# Entornos virtuales y pip dentro de contenedores

[🇬🇧 English](03-python-labs.md) · [🇨🇴 Español](03-python-labs.es.md) · [↩ Podman](README.es.md)

**Plataforma:** Podman 4.x/5.x en Linux con Python 3.12 dentro de la imagen indicada. Los comandos Python no son subcomandos de Podman.

## `podman run --rm -v "$PWD:/workspace:Z" -w /workspace docker.io/library/python:3.12-slim python -m venv .venv`

```bash
podman run --rm -v "$PWD:/workspace:Z" -w /workspace docker.io/library/python:3.12-slim python -m venv .venv
```

- **Sirve para:** Crear el entorno virtual Python `.venv` dentro de la carpeta del proyecto del host, ejecutando Python en un contenedor temporal Podman.
- **Parámetros:** `run`: crear contenedor; `--rm`: eliminarlo al salir; `-v "$PWD:/workspace:Z"`: montar directorio actual con reetiquetado SELinux privado (puede cambiar etiquetas del host); `-w /workspace`: directorio de trabajo; `python -m venv .venv`: crear el entorno en el volumen montado.
- **Ejemplo de uso:** Desde un proyecto de laboratorio confiable, crear `.venv` para scripts NetBox. Revisar SELinux, propietarios y permisos del host; usar la misma imagen después, ya que el entorno no necesariamente funciona fuera del contenedor.
- **Referencia oficial:** https://docs.podman.io/en/latest/markdown/podman-run.1.html

> Pendiente de validación en laboratorio.
