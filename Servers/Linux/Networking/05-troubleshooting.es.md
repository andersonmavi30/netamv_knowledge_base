---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Diagnóstico de enlaces y captura

[🇬🇧 English](05-troubleshooting.md) · [🇨🇴 Español](05-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Linux (Rocky/RHEL, Ubuntu, Debian); comprueba instalación y versión de utilidades.

## `ethtool eth0`

```bash
ethtool eth0
```

- **Sirve para:** Mostrar velocidad, dúplex, autonegociación y estado físico del enlace Ethernet cuando esté disponible.
- **Parámetros:** `eth0`: nombre de interfaz de ejemplo; reemplázalo por el nombre obtenido con `ip -br link show`; sin flags; solo consulta.
- **Ejemplo de uso:** Comprobar una NIC física con velocidad inesperada o pérdida de enlace.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ethtool.8.html

> Pendiente de validación en laboratorio.
