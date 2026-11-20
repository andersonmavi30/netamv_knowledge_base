# Linux Networking — RHEL / Rocky Linux / AlmaLinux / Fedora

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Networking](../README.es.md)

**Compatibilidad:** NetworkManager suele estar disponible en estas distribuciones; `nmcli` requiere que el servicio esté activo. `resolvectl` depende de `systemd-resolved` y no se presupone instalado.

- [Interfaces y direcciones](01-interfaces.es.md)
- [Enrutamiento y políticas](02-routing.es.md)
- [Sockets y puertos de escucha](03-sockets.es.md)
- [DNS y conexiones de red](04-dns-connections.es.md)
- [Diagnóstico de enlaces y captura](05-troubleshooting.es.md)

> Comandos existentes reorganizados, pendientes de validación en laboratorio. `eth0` es ilustrativo; verifica las interfaces. `tcpdump` requiere privilegios y autorización.
