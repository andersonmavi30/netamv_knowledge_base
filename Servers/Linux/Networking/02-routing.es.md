---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Enrutamiento y políticas

[🇬🇧 English](02-routing.md) · [🇨🇴 Español](02-routing.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Linux (Rocky/RHEL, Ubuntu, Debian); comprueba instalación y versión de utilidades.

## `ip route show`

```bash
ip route show
```

- **Sirve para:** Consultar rutas IPv4, gateway predeterminado y saltos siguientes de la tabla principal.
- **Parámetros:** `route`: información de rutas IPv4; `show`: muestra rutas sin modificarlas.
- **Ejemplo de uso:** Confirmar el gateway cuando un servidor no alcanza otra subred.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Pendiente de validación en laboratorio.

## `ip rule show`

```bash
ip rule show
```

- **Sirve para:** Listar reglas IPv4 de enrutamiento por políticas, prioridades y tablas asociadas.
- **Parámetros:** `rule`: base de reglas de routing; `show`: vista de consulta; las prioridades definen orden.
- **Ejemplo de uso:** Diagnosticar enrutamiento por origen en un servidor con múltiples NIC.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-rule.8.html

> Pendiente de validación en laboratorio.
