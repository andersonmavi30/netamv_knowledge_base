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
