---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Enrutamiento y políticas

[🇬🇧 English](02-routing.md) · [🇨🇴 Español](02-routing.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.es.md)

**Plataforma:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager suele estar disponible en estas distribuciones; `nmcli` requiere que el servicio esté activo. `resolvectl` depende de `systemd-resolved` y no se presupone instalado.

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

## `ip route get 1.1.1.1`

```bash
ip route get 1.1.1.1
```

- **Sirve para:** Mostrar la ruta elegida por el kernel, IP origen e interfaz de salida hacia un destino.
- **Parámetros:** `route get`: resolver sin agregar ruta; `1.1.1.1`: destino de ejemplo.
- **Ejemplo de uso:** Validar la interfaz de salida de un servidor multihomed.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Pendiente de validación en laboratorio.

## `ip -6 route show`

```bash
ip -6 route show
```

- **Sirve para:** Mostrar la tabla de rutas IPv6, incluida la ruta predeterminada cuando exista.
- **Parámetros:** `-6`: IPv6; `route`: rutas; `show`: solo consulta.
- **Ejemplo de uso:** Comprobar el gateway IPv6 predeterminado.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Pendiente de validación en laboratorio.
