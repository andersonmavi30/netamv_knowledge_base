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
