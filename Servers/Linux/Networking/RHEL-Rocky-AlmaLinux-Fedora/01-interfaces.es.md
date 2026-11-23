---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Interfaces y direcciones

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.es.md)

**Plataforma:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager suele estar disponible en estas distribuciones; `nmcli` requiere que el servicio esté activo. `resolvectl` depende de `systemd-resolved` y no se presupone instalado.

## `ip -br address show`

```bash
ip -br address show
```

- **Sirve para:** Mostrar interfaces y direcciones IPv4/IPv6 en formato compacto.
- **Parámetros:** `-br`: salida breve; `address`: información IP; `show`: consulta sin cambios.
- **Ejemplo de uso:** Comprobar direcciones de una VM Rocky Linux tras iniciar.
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

## `ip neigh show`

```bash
ip neigh show
```

- **Sirve para:** Listar entradas y estados de vecinos IPv4/IPv6 (ARP/ND).
- **Parámetros:** `neigh`: vecinos; `show`: consulta sin cambios.
- **Ejemplo de uso:** Comprobar la MAC del gateway y su estado.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-neighbour.8.html

> Pendiente de validación en laboratorio.

## `ip -d link show`

```bash
ip -d link show
```

- **Sirve para:** Mostrar atributos detallados del enlace, como información de VLAN, bridge o túneles cuando exista.
- **Parámetros:** `-d`: salida detallada; `link`: interfaces; `show`: consulta sin cambios.
- **Ejemplo de uso:** Inspeccionar identificadores VLAN o interfaces virtuales.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-link.8.html

> Pendiente de validación en laboratorio.

## `ip -4 addr show`

```bash
ip -4 addr show
```

- **Sirve para:** Listar únicamente direcciones IPv4 y sus interfaces asociadas.
- **Parámetros:** `-4`: familia IPv4; `addr`: direcciones de interfaces; `show`: consulta.
- **Ejemplo de uso:** Identificar direcciones IPv4 en un host con configuración dual-stack.
- **Referencia oficial:** https://man7.org/linux/man-pages/man8/ip-address.8.html

> Pendiente de validación en laboratorio.
