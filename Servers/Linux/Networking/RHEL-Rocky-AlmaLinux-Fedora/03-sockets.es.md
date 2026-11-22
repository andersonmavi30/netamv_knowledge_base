---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Sockets y puertos de escucha

[🇬🇧 English](03-sockets.md) · [🇨🇴 Español](03-sockets.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.es.md)

**Plataforma:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager suele estar disponible en estas distribuciones; `nmcli` requiere que el servicio esté activo. `resolvectl` depende de `systemd-resolved` y no se presupone instalado.

## `ss -tulpen`

```bash
ss -tulpen
```

- **Sirve para:** Listar sockets TCP/UDP en escucha, direcciones numéricas, procesos y detalles adicionales.
- **Parámetros:** `-t`: TCP; `-u`: UDP; `-l`: escucha; `-p`: procesos; `-e`: datos extra; `-n`: numérico; algunos procesos requieren privilegios.
- **Ejemplo de uso:** Verificar qué proceso escucha en TCP 443 o UDP 53.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.

## `ss -s`

```bash
ss -s
```

- **Sirve para:** Resumir cantidades de sockets y estados TCP.
- **Parámetros:** `-s`: estadísticas resumidas; solo consulta.
- **Ejemplo de uso:** Detectar demasiados sockets TCP o TIME-WAIT.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.
