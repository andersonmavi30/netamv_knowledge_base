---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# Interfaces y direcciones

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ Debian / Ubuntu Server](README.es.md)

**Plataforma:** Debian / Ubuntu Server. Ubuntu Server puede usar Netplan con `systemd-networkd`; Debian puede usar `ifupdown`, NetworkManager o systemd-networkd. `resolvectl` solo funciona si `systemd-resolved` está presente y activo; `nmcli` no es universal.

## `ip -br address show`

```bash
ip -br address show
```

- **Sirve para:** Mostrar interfaces y direcciones IPv4/IPv6 en formato compacto.
- **Parámetros:** `-br`: salida breve; `address`: información IP; `show`: consulta sin cambios.
- **Ejemplo de uso:** Comprobar direcciones de una VM Debian/Ubuntu Server tras iniciar.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-address.8.html

> Pendiente de validación en laboratorio.

## `ip -br link show`

```bash
ip -br link show
```

- **Sirve para:** Mostrar interfaces, estados administrativos/de enlace e identificadores de capa 2 en forma resumida.
- **Parámetros:** `-br`: salida breve; `link`: estado de enlace; `show`: solo consulta.
- **Ejemplo de uso:** Identificar una NIC caída en un servidor Linux de virtualización.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-link.8.html

> Pendiente de validación en laboratorio.

## `ip -s link show`

```bash
ip -s link show
```

- **Sirve para:** Mostrar contadores RX/TX, errores y paquetes descartados por interfaz.
- **Parámetros:** `-s`: estadísticas; `link`: interfaces; `show`: consulta.
- **Ejemplo de uso:** Detectar descartes al investigar enlaces lentos.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-link.8.html

> Pendiente de validación en laboratorio.
