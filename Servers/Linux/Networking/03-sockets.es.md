---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Sockets y puertos de escucha

[🇬🇧 English](03-sockets.md) · [🇨🇴 Español](03-sockets.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Linux (Rocky/RHEL, Ubuntu, Debian); comprueba instalación y versión de utilidades.

## `ss -tulpen`

```bash
ss -tulpen
```

- **Sirve para:** Listar sockets TCP/UDP en escucha, direcciones numéricas, procesos y detalles adicionales.
- **Parámetros:** `-t`: TCP; `-u`: UDP; `-l`: escucha; `-p`: procesos; `-e`: datos extra; `-n`: numérico; algunos procesos requieren privilegios.
- **Ejemplo de uso:** Verificar qué proceso escucha en TCP 443 o UDP 53.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.
