---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# Sockets and listening ports

[🇬🇧 English](03-sockets.md) · [🇨🇴 Español](03-sockets.es.md) · [↩ Debian / Ubuntu Server](README.md)

**Platform:** Debian / Ubuntu Server. Ubuntu Server may use Netplan with `systemd-networkd`; Debian can use ifupdown, NetworkManager, or systemd-networkd. `resolvectl` only works with active `systemd-resolved`; `nmcli` is not universal.

## `ss -tulpen`

```bash
ss -tulpen
```

- **Purpose:** List listening TCP/UDP sockets with numeric addresses, process details and extended socket information.
- **Arguments:** `-t`: TCP; `-u`: UDP; `-l`: listening; `-p`: processes; `-e`: extended info; `-n`: numeric; some process data needs elevated permissions.
- **Use case:** Check which service owns TCP 443 or UDP 53 during troubleshooting.
- **Official reference:** https://man7.org/linux/man-pages/man8/ss.8.html

> Not lab-verified.
