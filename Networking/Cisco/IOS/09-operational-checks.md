---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Operational checks — expanded · Cisco IOS

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** Classic IOS (device and feature dependent). Commands have not been tested on devices; confirm syntax using `?` and release-specific docs.

## CEF forwarding lookup

```text
show ip cef 198.51.100.10
```

- **Purpose:** Inspect the FIB's forwarding result for a destination.
- **Parameters / flags:** IP: destination host; CEF must be enabled.
- **Operational use:** Compare installed forwarding with the expected route.
- **Filter / check:** `show ip cef 198.51.100.10`

## EIGRP adjacency check

```text
show ip eigrp neighbors | include 192.0.2
```

- **Purpose:** View EIGRP neighbors, uptime and queue information.
- **Parameters / flags:** neighbors: peer list; requires EIGRP.
- **Operational use:** Find a missing EIGRP neighbor after a change.
- **Filter / check:** `show ip eigrp neighbors | include 192.0.2`

## NAT translation lookup

```text
show ip nat translations | include 192.0.2.10
```

- **Purpose:** Inspect current inside/outside NAT translation entries.
- **Parameters / flags:** translations: active translation table; NAT must be configured.
- **Operational use:** Find sessions for a specific inside host.
- **Filter / check:** `show ip nat translations | include 192.0.2.10`

## CPU-heavy processes

```text
show processes cpu sorted | include CPU|IP Input
```

- **Purpose:** List processes ordered by CPU use on supporting IOS platforms.
- **Parameters / flags:** sorted: order by CPU consumption.
- **Operational use:** Identify which process caused a high CPU alert.
- **Filter / check:** `show processes cpu sorted | include CPU|IP Input`

## Operational trunk VLANs

```text
show interfaces trunk | include 10
```

- **Purpose:** Show trunk state, native VLAN and allowed VLANs on switches.
- **Parameters / flags:** trunk: list operational trunk interfaces; switching feature required.
- **Operational use:** Find why VLAN 10 is not carried over the uplink.
- **Filter / check:** `show interfaces trunk | include 10`

> ⚠️ Feature-specific commands may return no information if the feature is not configured. Stop interactive monitors when finished.

**Reference**: [Cisco IOS](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-software/products-command-reference-list.html)
