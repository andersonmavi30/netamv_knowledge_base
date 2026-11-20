---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# DNS and network connections

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ Index](README.md)

**Platform:** Linux (Rocky/RHEL, Ubuntu, Debian); verify tool availability and version.

## `resolvectl status`

```bash
resolvectl status
```

- **Purpose:** Inspect DNS servers, domains and resolver settings for systemd-resolved and its links.
- **Arguments:** `status`: display resolver and per-link DNS state; requires systemd-resolved/resolvectl availability.
- **Use case:** Investigate unexpected DNS resolution on an Ubuntu host.
- **Official reference:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Not lab-verified.
