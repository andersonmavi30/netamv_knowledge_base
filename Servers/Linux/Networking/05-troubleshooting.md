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

## `sudo tcpdump -ni eth0 -c 20`

```bash
sudo tcpdump -ni eth0 -c 20
```

- **Purpose:** Capture and display up to 20 packets on a designated interface for short, authorized troubleshooting.
- **Arguments:** `sudo`: capture privileges; `-n`: no DNS/name resolution; `-i eth0`: select interface; `-c 20`: stop after 20 packets. May expose sensitive traffic.
- **Use case:** Inspect short DNS/connection troubleshooting traffic on a lab server; replace interface and use only with authorization.
- **Official reference:** https://www.tcpdump.org/manpages/tcpdump.1.html

> Not lab-verified.
