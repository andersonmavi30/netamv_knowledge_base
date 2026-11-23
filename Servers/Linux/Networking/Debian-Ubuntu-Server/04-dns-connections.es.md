---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# DNS y conexiones de red

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ Debian / Ubuntu Server](README.es.md)

**Plataforma:** Debian / Ubuntu Server. Ubuntu Server puede usar Netplan con `systemd-networkd`; Debian puede usar `ifupdown`, NetworkManager o systemd-networkd. `resolvectl` solo funciona si `systemd-resolved` está presente y activo; `nmcli` no es universal.

## `resolvectl status`

```bash
resolvectl status
```

- **Sirve para:** Consultar servidores DNS, dominios y opciones del resolvedor de systemd por interfaz.
- **Parámetros:** `status`: consulta estado DNS global y por interfaz; requiere `resolvectl` y systemd-resolved.
- **Ejemplo de uso:** Investigar resolución DNS inesperada en Ubuntu.
- **Referencia oficial:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Pendiente de validación en laboratorio.

## `resolvectl query example.com`

```bash
resolvectl query example.com
```

- **Sirve para:** Resolver un dominio mediante systemd-resolved y mostrar el resultado.
- **Parámetros:** `query`: consulta DNS; `example.com`: dominio de ejemplo; requiere systemd-resolved activo.
- **Ejemplo de uso:** Comprobar la resolución DNS en Ubuntu Server.
- **Referencia oficial:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Pendiente de validación en laboratorio.

## `getent ahosts example.com`

```bash
getent ahosts example.com
```

- **Sirve para:** Resolver un nombre mediante Name Service Switch (NSS) y mostrar direcciones y tipos de socket.
- **Parámetros:** `ahosts`: consulta de nombres mediante getaddrinfo/NSS; `example.com`: nombre de ejemplo. Puede usar fuentes distintas a DNS.
- **Ejemplo de uso:** Comparar la resolución de nombres del sistema con el comportamiento de una aplicación.
- **Referencia oficial:** https://man7.org/linux/man-pages/man1/getent.1.html

> Pendiente de validación en laboratorio.
