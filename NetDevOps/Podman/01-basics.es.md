---
tags: [podman, containers, netdevops, cli]
validation: not-lab-verified
---

# CLI de Podman e información del host

[🇬🇧 English](01-basics.md) · [🇨🇴 Español](01-basics.es.md) · [↩ Podman](README.es.md)

**Plataforma:** Podman 4.x/5.x en Linux; la compatibilidad puede variar por versión.

## `podman --version`

```bash
podman --version
```

- **Sirve para:** Consultar la versión instalada de Podman antes de ejecutar automatizaciones.
- **Parámetros:** `--version`: imprime la versión y termina; no realiza cambios.
- **Ejemplo de uso:** Confirmar la versión de Podman en una VM de Agentic/NetDevOps antes de ejecutar un laboratorio.
- **Referencia oficial:** https://docs.podman.io/en/latest/markdown/podman.1.html

> Pendiente de validación en laboratorio.

## `podman info`

```bash
podman info
```

- **Sirve para:** Consultar configuración de host, almacenamiento, runtime y registros de Podman.
- **Parámetros:** `info`: muestra detalles del host y runtime; solo consulta. Puede revelar rutas locales y registros.
- **Ejemplo de uso:** Comprobar modo rootless, driver de almacenamiento y runtime OCI antes de desplegar automatización.
- **Referencia oficial:** https://docs.podman.io/en/latest/markdown/podman-info.1.html

> Pendiente de validación en laboratorio.
