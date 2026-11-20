---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Diagnóstico de enlaces y captura

[🇬🇧 English](05-troubleshooting.md) · [🇨🇴 Español](05-troubleshooting.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.es.md)

**Plataforma:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager suele estar disponible en estas distribuciones; `nmcli` requiere que el servicio esté activo. `resolvectl` depende de `systemd-resolved` y no se presupone instalado.

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
