---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# DNS and network connections

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ Debian / Ubuntu Server](README.md)

**Platform:** Debian / Ubuntu Server. Ubuntu Server may use Netplan with `systemd-networkd`; Debian can use ifupdown, NetworkManager, or systemd-networkd. `resolvectl` only works with active `systemd-resolved`; `nmcli` is not universal.

## `resolvectl status`

```bash
resolvectl status
```

- **Purpose:** Inspect DNS servers, domains and resolver settings for systemd-resolved and its links.
- **Arguments:** `status`: display resolver and per-link DNS state; requires systemd-resolved/resolvectl availability.
- **Use case:** Investigate unexpected DNS resolution on an Ubuntu host.
- **Official reference:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Not lab-verified.
