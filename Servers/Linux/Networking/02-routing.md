---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# Routing and policy rules

[🇬🇧 English](02-routing.md) · [🇨🇴 Español](02-routing.es.md) · [↩ Index](README.md)

**Platform:** Linux (Rocky/RHEL, Ubuntu, Debian); verify tool availability and version.

## `ip route show`

```bash
ip route show
```

- **Purpose:** Inspect the main IPv4 routing table, including default gateway and next hops.
- **Arguments:** `route`: IPv4 routing information; `show`: display routes, without modifying them.
- **Use case:** Confirm the default gateway when a server cannot reach another subnet.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Not lab-verified.
