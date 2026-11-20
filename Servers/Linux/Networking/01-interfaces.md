---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Interfaces and addresses

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ Index](README.md)

**Platform:** Linux (Rocky/RHEL, Ubuntu, Debian); verify tool availability and version.

## `ip -br address show`

```bash
ip -br address show
```

- **Purpose:** Display interfaces and IPv4/IPv6 addresses in a compact table.
- **Arguments:** `-br`: brief output; `address`: IP information; `show`: read-only display.
- **Use case:** Check a Rocky Linux VM's addresses after boot.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-address.8.html

> Not lab-verified.
