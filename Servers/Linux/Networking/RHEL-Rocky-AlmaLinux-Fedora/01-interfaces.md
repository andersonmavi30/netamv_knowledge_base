---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Interfaces and addresses

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.md)

**Platform:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager is commonly used on these distributions; `nmcli` requires the service to be active. `resolvectl` depends on `systemd-resolved` and is not assumed to be installed.

## `ip -br address show`

```bash
ip -br address show
```

- **Purpose:** Display interfaces and IPv4/IPv6 addresses in a compact table.
- **Arguments:** `-br`: brief output; `address`: IP information; `show`: read-only display.
- **Use case:** Check a Rocky Linux VM's addresses after boot.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-address.8.html

> Not lab-verified.

## `ip -br link show`

```bash
ip -br link show
```

- **Purpose:** Show network interface names, administrative/link state and link-layer identifiers in concise form.
- **Arguments:** `-br`: brief display; `link`: link-layer status; `show`: read-only.
- **Use case:** Identify a down NIC on a Linux virtualization host.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-link.8.html

> Not lab-verified.
