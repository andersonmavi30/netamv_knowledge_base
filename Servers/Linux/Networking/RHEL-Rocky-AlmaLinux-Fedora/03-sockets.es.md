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

## `ss -tn state established`

```bash
ss -tn state established
```

- **Sirve para:** Mostrar sockets TCP establecidos con direcciones y puertos numéricos.
- **Parámetros:** `-t`: TCP; `-n`: formato numérico; `state established`: solo ESTABLISHED.
- **Ejemplo de uso:** Inspeccionar sesiones TCP activas de aplicaciones.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.

## `ss -ltnp`

```bash
ss -ltnp
```

- **Sirve para:** Listar sockets TCP en escucha, direcciones numéricas y procesos asociados cuando los permisos lo permitan.
- **Parámetros:** `-l`: escucha; `-t`: TCP; `-n`: numérico; `-p`: procesos (puede requerir sudo).
- **Ejemplo de uso:** Identificar el proceso que utiliza un puerto de servicio.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.

## `ss -uan`

```bash
ss -uan
```

- **Sirve para:** Listar sockets UDP con direcciones y puertos numéricos.
- **Parámetros:** `-u`: UDP; `-a`: todos los estados; `-n`: sin resolución de nombres.
- **Ejemplo de uso:** Inspeccionar sockets UDP de servicios DNS, DHCP o monitoreo.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ss.8.html

> Pendiente de validación en laboratorio.
