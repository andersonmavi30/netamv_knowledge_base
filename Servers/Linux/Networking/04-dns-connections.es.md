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

## `nmcli device status`

```bash
nmcli device status
```

- **Sirve para:** Mostrar dispositivos gestionados por NetworkManager y sus conexiones activas.
- **Parámetros:** `device`: dispositivos de red; `status`: estado actual; requiere NetworkManager.
- **Ejemplo de uso:** Comprobar si una NIC de Rocky/RHEL está conectada o no administrada.
- **Referencia oficial:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Pendiente de validación en laboratorio.

## `nmcli connection show --active`

```bash
nmcli connection show --active
```

- **Sirve para:** Listar los perfiles de conexión activos de NetworkManager y sus dispositivos.
- **Parámetros:** `connection show`: muestra conexiones; `--active`: filtra únicamente los perfiles activos; solo consulta.
- **Ejemplo de uso:** Identificar el perfil de red activo antes de diagnosticar un servidor RHEL.
- **Referencia oficial:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Pendiente de validación en laboratorio.
