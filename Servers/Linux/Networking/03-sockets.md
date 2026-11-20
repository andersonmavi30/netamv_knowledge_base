---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Sockets and listening ports

[🇬🇧 English](03-sockets.md) · [🇨🇴 Español](03-sockets.es.md) · [↩ Index](README.md)

**Platform:** Linux (Rocky/RHEL, Ubuntu, Debian); verify tool availability and version.

## `ss -tulpen`

```bash
ss -tulpen
```

- **Purpose:** List listening TCP/UDP sockets with numeric addresses, process details and extended socket information.
- **Arguments:** `-t`: TCP; `-u`: UDP; `-l`: listening; `-p`: processes; `-e`: extended info; `-n`: numeric; some process data needs elevated permissions.
- **Use case:** Check which service owns TCP 443 or UDP 53 during troubleshooting.
- **Official reference:** https://man7.org/linux/man-pages/man8/ss.8.html

> Not lab-verified.
