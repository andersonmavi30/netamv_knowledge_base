# Linux Networking — Debian / Ubuntu Server

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Networking](../README.es.md)

**Compatibilidad:** Ubuntu Server puede usar Netplan con `systemd-networkd`; Debian puede usar `ifupdown`, NetworkManager o systemd-networkd. `resolvectl` solo funciona si `systemd-resolved` está presente y activo; `nmcli` no es universal.

- [Interfaces y direcciones](01-interfaces.es.md)
- [Enrutamiento y políticas](02-routing.es.md)
- [Sockets y puertos de escucha](03-sockets.es.md)
- [DNS y conexiones de red](04-dns-connections.es.md)
- [Diagnóstico de enlaces y captura](05-troubleshooting.es.md)

> Comandos existentes reorganizados, pendientes de validación en laboratorio. `eth0` es ilustrativo; verifica las interfaces. `tcpdump` requiere privilegios y autorización.
