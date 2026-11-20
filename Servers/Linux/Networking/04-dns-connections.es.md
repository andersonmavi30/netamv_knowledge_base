---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# DNS y conexiones de red

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Linux (Rocky/RHEL, Ubuntu, Debian); comprueba instalación y versión de utilidades.

## `resolvectl status`

```bash
resolvectl status
```

- **Sirve para:** Consultar servidores DNS, dominios y opciones del resolvedor de systemd por interfaz.
- **Parámetros:** `status`: consulta estado DNS global y por interfaz; requiere `resolvectl` y systemd-resolved.
- **Ejemplo de uso:** Investigar resolución DNS inesperada en Ubuntu.
- **Referencia oficial:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Pendiente de validación en laboratorio.
