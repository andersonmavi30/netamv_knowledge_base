---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Sockets and listening ports

[🇬🇧 English](03-sockets.md) · [🇨🇴 Español](03-sockets.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.md)

**Platform:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager is commonly used on these distributions; `nmcli` requires the service to be active. `resolvectl` depends on `systemd-resolved` and is not assumed to be installed.

## `ss -tulpen`

```bash
ss -tulpen
```

- **Purpose:** List listening TCP/UDP sockets with numeric addresses, process details and extended socket information.
- **Arguments:** `-t`: TCP; `-u`: UDP; `-l`: listening; `-p`: processes; `-e`: extended info; `-n`: numeric; some process data needs elevated permissions.
- **Use case:** Check which service owns TCP 443 or UDP 53 during troubleshooting.
- **Official reference:** https://man7.org/linux/man-pages/man8/ss.8.html

> Not lab-verified.

## `ss -s`

```bash
ss -s
```

- **Purpose:** Summarize socket counts and TCP connection states.
- **Arguments:** `-s`: summary statistics; read-only.
- **Use case:** Spot unusually high TIME-WAIT or TCP counts.
- **Official reference:** https://man7.org/linux/man-pages/man8/ss.8.html

> Not lab-verified.

## `ss -tn state established`

```bash
ss -tn state established
```

- **Purpose:** Show established TCP sockets with numeric addresses and ports.
- **Arguments:** `-t`: TCP; `-n`: numeric; `state established`: ESTABLISHED only.
- **Use case:** Inspect active application TCP sessions.
- **Official reference:** https://man7.org/linux/man-pages/man8/ss.8.html

> Not lab-verified.

## `ss -ltnp`

```bash
ss -ltnp
```

- **Purpose:** List listening TCP sockets with numeric addresses and owning process information when permissions permit.
- **Arguments:** `-l`: listening; `-t`: TCP; `-n`: numeric; `-p`: process information (may require sudo).
- **Use case:** Find the process bound to a service port.
- **Official reference:** https://man7.org/linux/man-pages/man8/ss.8.html

> Not lab-verified.
