---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Interfaces y direcciones

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Linux (Rocky/RHEL, Ubuntu, Debian); comprueba instalación y versión de utilidades.

## `ip -br address show`

```bash
ip -br address show
```

- **Sirve para:** Mostrar interfaces y direcciones IPv4/IPv6 en formato compacto.
- **Parámetros:** `-br`: salida breve; `address`: información IP; `show`: consulta sin cambios.
- **Ejemplo de uso:** Comprobar direcciones de una VM Rocky Linux tras iniciar.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-address.8.html

> Pendiente de validación en laboratorio.
