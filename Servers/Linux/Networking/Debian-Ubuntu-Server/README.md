# Linux Networking — Debian / Ubuntu Server

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Networking](../README.md)

**Compatibility:** Ubuntu Server may use Netplan with `systemd-networkd`; Debian can use ifupdown, NetworkManager, or systemd-networkd. `resolvectl` only works with active `systemd-resolved`; `nmcli` is not universal.

- [Interfaces and addresses](01-interfaces.md)
- [Routing and policy rules](02-routing.md)
- [Sockets and listening ports](03-sockets.md)
- [DNS and network connections](04-dns-connections.md)
- [Link diagnostics and packet capture](05-troubleshooting.md)

> Existing commands reorganized; pending lab verification. `eth0` is illustrative; verify interfaces. `tcpdump` requires privileges and authorization.
