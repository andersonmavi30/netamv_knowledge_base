---
tags: [cli, fortinet, fortios, show]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔎 Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Fortinet](../README.md)

**Platform:** Fortinet / FortiOS · **Compatibility:** FortiOS 7.x (verify your exact release).

## `get system status`

```text
get system status | grep -i hostname
```

- **Purpose:** Show hostname, firmware and system identifiers.
- **Arguments:** No arguments.
- **Use case:** Identify the firmware before troubleshooting.

- **Practical filter:** `get system status | grep -i hostname` — Locate hostname quickly.

## `get system performance status`

```text
get system performance status | grep -i cpu
```

- **Purpose:** Check CPU, memory, uptime and session statistics.
- **Arguments:** No arguments.
- **Use case:** Quick health check.

- **Practical filter:** `get system performance status | grep -i cpu` — Focus on CPU-related lines.

## `get system interface`

```text
get system interface | grep -i port3
```

- **Purpose:** List interface status and addressing.
- **Arguments:** No arguments.
- **Use case:** Find an interface IP.

- **Practical filter:** `get system interface | grep -i port3` — Find port3; other properties may require full output.

## `get router info routing-table all`

```text
get router info routing-table all | grep 198.51.100
```

- **Purpose:** Display the routing table.
- **Arguments:** all: show routes across protocols.
- **Use case:** Validate the next hop for a destination.

- **Practical filter:** `get router info routing-table all | grep 198.51.100` — Find a prefix; text filtering is not a forwarding lookup.

## `get system arp`

```text
get system arp | grep 192.0.2.10
```

- **Purpose:** Inspect the IPv4 ARP table and find the MAC address and interface associated with an IP.
- **Arguments:** `grep 192.0.2.10`: show only lines containing that IP; this is a text filter.
- **Use case:** Verify whether the FortiGate has learned a gateway or server MAC before troubleshooting connectivity.
- **Caution:** A missing match can mean no active ARP entry; check the relevant interface and VDOM.


> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
