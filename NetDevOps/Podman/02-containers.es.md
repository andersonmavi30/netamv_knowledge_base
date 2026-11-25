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

## `podman run -d --name web-lab -p 127.0.0.1:8080:80 docker.io/library/nginx:stable-alpine`

```bash
podman run -d --name web-lab -p 127.0.0.1:8080:80 docker.io/library/nginx:stable-alpine
```

- **Sirve para:** Crear e iniciar un contenedor Nginx, exponiendo HTTP solo en loopback del host.
- **Parámetros:** `run`: crear e iniciar; `-d`: segundo plano; `--name web-lab`: nombre; `-p 127.0.0.1:8080:80`: puerto 8080 de loopback al puerto 80 del contenedor; `docker.io/library/nginx:stable-alpine`: imagen completa.
- **Ejemplo de uso:** Levantar un servicio HTTP local para pruebas NetDevOps; requiere puerto 8080 disponible y acceso a la imagen.
- **Referencia oficial:** https://docs.podman.io/en/latest/markdown/podman-run.1.html

> Pendiente de validación en laboratorio.

## `podman logs --tail 30 web-lab`

```bash
podman logs --tail 30 web-lab
```

- **Sirve para:** Consultar las últimas 30 líneas del registro del contenedor indicado.
- **Parámetros:** `logs`: ver salida del contenedor; `--tail 30`: últimas 30 líneas; `web-lab`: nombre del contenedor.
- **Ejemplo de uso:** Revisar errores de inicio o accesos HTTP tras una prueba de monitoreo fallida; los logs pueden contener datos sensibles.
- **Referencia oficial:** https://docs.podman.io/en/latest/markdown/podman-logs.1.html

> Pendiente de validación en laboratorio.
