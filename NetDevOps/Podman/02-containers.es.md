---
tags: [podman, containers, netdevops, cli]
validation: not-lab-verified
---

# Contenedores y diagnóstico

[🇬🇧 English](02-containers.md) · [🇨🇴 Español](02-containers.es.md) · [↩ Podman](README.es.md)

**Plataforma:** Podman 4.x/5.x en Linux; puede variar según la versión.

## `podman ps -a`

```bash
podman ps -a
```

- **Sirve para:** Listar contenedores activos y detenidos con sus estados, ID y nombres.
- **Parámetros:** `ps`: listar contenedores; `-a` / `--all`: incluir contenedores detenidos.
- **Ejemplo de uso:** Encontrar un servicio de laboratorio detenido antes de diagnosticar una tarea de automatización.
- **Referencia oficial:** https://docs.podman.io/en/latest/markdown/podman-ps.1.html

> Pendiente de validación en laboratorio.
