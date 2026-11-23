---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# Diagnóstico de enlaces y captura

[🇬🇧 English](05-troubleshooting.md) · [🇨🇴 Español](05-troubleshooting.es.md) · [↩ Debian / Ubuntu Server](README.es.md)

**Plataforma:** Debian / Ubuntu Server. Ubuntu Server puede usar Netplan con `systemd-networkd`; Debian puede usar `ifupdown`, NetworkManager o systemd-networkd. `resolvectl` solo funciona si `systemd-resolved` está presente y activo; `nmcli` no es universal.

## `ethtool eth0`

```bash
ethtool eth0
```

- **Sirve para:** Mostrar velocidad, dúplex, autonegociación y estado físico del enlace Ethernet cuando esté disponible.
- **Parámetros:** `eth0`: nombre de interfaz de ejemplo; reemplázalo por el nombre obtenido con `ip -br link show`; sin flags; solo consulta.
- **Ejemplo de uso:** Comprobar una NIC física con velocidad inesperada o pérdida de enlace.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ethtool.8.html

> Pendiente de validación en laboratorio.

## `sudo tcpdump -ni eth0 -c 20`

```bash
sudo tcpdump -ni eth0 -c 20
```

- **Sirve para:** Capturar y mostrar hasta 20 paquetes en una interfaz designada para un diagnóstico breve y autorizado.
- **Parámetros:** `sudo`: privilegios de captura; `-n`: evita resolución de nombres; `-i eth0`: interfaz; `-c 20`: termina después de 20 paquetes. Puede exponer tráfico sensible.
- **Ejemplo de uso:** Revisar brevemente tráfico de diagnóstico en un servidor de laboratorio; adaptar la interfaz y contar con autorización.
- **Referencia oficial:** https://www.tcpdump.org/manpages/tcpdump.1.html

> Pendiente de validación en laboratorio.

## `ethtool -i eth0`

```bash
ethtool -i eth0
```

- **Sirve para:** Mostrar controlador, versión del firmware y datos de bus de la NIC cuando estén disponibles.
- **Parámetros:** `-i`: consultar detalles del controlador; `eth0`: interfaz de ejemplo; reemplazar por la NIC real. Depende del dispositivo.
- **Ejemplo de uso:** Comprobar controlador y firmware de una tarjeta de red Linux.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ethtool.8.html

> Pendiente de validación en laboratorio.

## `ethtool -S eth0`

```bash
ethtool -S eth0
```

- **Sirve para:** Mostrar contadores específicos del controlador de la NIC cuando estén disponibles.
- **Parámetros:** `-S`: consultar estadísticas del dispositivo; `eth0`: interfaz de ejemplo. Los contadores varían según NIC/controlador.
- **Ejemplo de uso:** Investigar errores de colas o descartes de paquetes en una NIC.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ethtool.8.html

> Pendiente de validación en laboratorio.
