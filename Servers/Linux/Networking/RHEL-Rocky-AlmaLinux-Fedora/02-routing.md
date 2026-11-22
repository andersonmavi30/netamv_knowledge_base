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

## `ip route get 1.1.1.1`

```bash
ip route get 1.1.1.1
```

- **Purpose:** Show the kernel's selected route, source IP and egress interface to a destination.
- **Arguments:** `route get`: resolve without adding a route; `1.1.1.1`: example destination.
- **Use case:** Validate outbound interface on a multi-homed server.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Not lab-verified.

## `ip -6 route show`

```bash
ip -6 route show
```

- **Purpose:** Display the IPv6 routing table, including its default route when present.
- **Arguments:** `-6`: IPv6; `route`: routes; `show`: read-only.
- **Use case:** Check IPv6 default gateway.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-route.8.html

> Not lab-verified.
