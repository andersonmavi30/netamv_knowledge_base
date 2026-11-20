---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# Routing and policy rules

[🇬🇧 English](02-routing.md) · [🇨🇴 Español](02-routing.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.md)

**Platform:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager is commonly used on these distributions; `nmcli` requires the service to be active. `resolvectl` depends on `systemd-resolved` and is not assumed to be installed.

## `ip route show`

```bash
ip route show
```

- **Purpose:** Inspect the main IPv4 routing table, including default gateway and next hops.
- **Arguments:** `route`: IPv4 routing information; `show`: display routes, without modifying them.
- **Use case:** Confirm the default gateway when a server cannot reach another subnet.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Not lab-verified.

## `ip rule show`

```bash
ip rule show
```

- **Purpose:** List IPv4 policy-routing rules, their priorities and associated routing tables.
- **Arguments:** `rule`: routing policy database; `show`: read-only view; priorities influence rule order.
- **Use case:** Diagnose source-based routing on a multi-homed server.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-rule.8.html

> Not lab-verified.
