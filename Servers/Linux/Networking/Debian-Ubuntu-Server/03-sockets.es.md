---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# Sockets y puertos de escucha

[🇬🇧 English](03-sockets.md) · [🇨🇴 Español](03-sockets.es.md) · [↩ Debian / Ubuntu Server](README.es.md)

**Plataforma:** Debian / Ubuntu Server. Ubuntu Server puede usar Netplan con `systemd-networkd`; Debian puede usar `ifupdown`, NetworkManager o systemd-networkd. `resolvectl` solo funciona si `systemd-resolved` está presente y activo; `nmcli` no es universal.

## `ss -tulpen`

```bash
ss -tulpen
```

- **Sirve para:** Listar sockets TCP/UDP en escucha, direcciones numéricas, procesos y detalles adicionales.
- **Parámetros:** `-t`: TCP; `-u`: UDP; `-l`: escucha; `-p`: procesos; `-e`: datos extra; `-n`: numérico; algunos procesos requieren privilegios.
- **Ejemplo de uso:** Verificar qué proceso escucha en TCP 443 o UDP 53.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.
