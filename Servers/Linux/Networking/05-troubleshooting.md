---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Link diagnostics and packet capture

[🇬🇧 English](05-troubleshooting.md) · [🇨🇴 Español](05-troubleshooting.es.md) · [↩ Index](README.md)

**Platform:** Linux (Rocky/RHEL, Ubuntu, Debian); verify tool availability and version.

## `ethtool eth0`

```bash
ethtool eth0
```

- **Purpose:** Display Ethernet link speed, duplex, autonegotiation and link status when supported.
- **Arguments:** `eth0`: example interface name; replace it with an interface shown by `ip -br link show`; no flags; read-only.
- **Use case:** Check a physical server NIC with unexpected speed or link loss.
- **Official reference:** https://man7.org/linux/man-pages/man8/ethtool.8.html

> Not lab-verified.
