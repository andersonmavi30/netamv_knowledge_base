---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# DNS y conexiones de red

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.es.md)

**Plataforma:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager suele estar disponible en estas distribuciones; `nmcli` requiere que el servicio esté activo. `resolvectl` depende de `systemd-resolved` y no se presupone instalado.

## `nmcli device status`

```bash
nmcli device status
```

- **Sirve para:** Mostrar dispositivos gestionados por NetworkManager y sus conexiones activas.
- **Parámetros:** `device`: dispositivos de red; `status`: estado actual; requiere NetworkManager.
- **Ejemplo de uso:** Comprobar si una NIC de Rocky/RHEL está conectada o no administrada.
- **Referencia oficial:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Pendiente de validación en laboratorio.

## `nmcli connection show --active`

```bash
nmcli connection show --active
```

- **Sirve para:** Listar los perfiles de conexión activos de NetworkManager y sus dispositivos.
- **Parámetros:** `connection show`: muestra conexiones; `--active`: filtra únicamente los perfiles activos; solo consulta.
- **Ejemplo de uso:** Identificar el perfil de red activo antes de diagnosticar un servidor RHEL.
- **Referencia oficial:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Pendiente de validación en laboratorio.

## `nmcli -f GENERAL,IP4 device show eth0`

```bash
nmcli -f GENERAL,IP4 device show eth0
```

- **Sirve para:** Mostrar propiedades generales y configuración IPv4 de un dispositivo de NetworkManager.
- **Parámetros:** `-f GENERAL,IP4`: seleccionar campos; `device show`: consultar propiedades; `eth0`: interfaz de ejemplo. Requiere NetworkManager.
- **Ejemplo de uso:** Revisar IP y gateway IPv4 de una interfaz RHEL.
- **Referencia oficial:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Pendiente de validación en laboratorio.

## `nmcli -f IP4.DNS device show eth0`

```bash
nmcli -f IP4.DNS device show eth0
```

- **Sirve para:** Mostrar servidores DNS IPv4 asignados a un dispositivo NetworkManager.
- **Parámetros:** `-f IP4.DNS`: solo DNS; `device show`: consultar; `eth0`: interfaz de ejemplo. Requiere NetworkManager.
- **Ejemplo de uso:** Verificar los DNS asignados a una interfaz Rocky Linux.
- **Referencia oficial:** https://networkmanager.dev/docs/api/latest/nmcli.html

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
