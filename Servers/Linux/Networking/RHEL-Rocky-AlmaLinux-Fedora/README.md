# Linux Networking — RHEL / Rocky Linux / AlmaLinux / Fedora

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Networking](../README.md)

**Compatibility:** NetworkManager is commonly used on these distributions; `nmcli` requires the service to be active. `resolvectl` depends on `systemd-resolved` and is not assumed to be installed.

- [Interfaces and addresses](01-interfaces.md)
- [Routing and policy rules](02-routing.md)
- [Sockets and listening ports](03-sockets.md)
- [DNS and network connections](04-dns-connections.md)
- [Link diagnostics and packet capture](05-troubleshooting.md)

> Existing commands reorganized; pending lab verification. `eth0` is illustrative; verify interfaces. `tcpdump` requires privileges and authorization.
