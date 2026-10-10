---
tags: [cli, fortinet, fortios, show]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔎 Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Fortinet](../README.md)

**Platform:** Fortinet / FortiOS · **Compatibility:** FortiOS 7.4 (examples; verify your release).

## `get system status`

```text
get system status
```

- **Purpose:** Show hostname, firmware and system identifiers.
- **Arguments:** No arguments.
- **Use case:** Identify the firmware before troubleshooting.

## `get system performance status`

```text
get system performance status
```

- **Purpose:** Check CPU, memory, uptime and session statistics.
- **Arguments:** No arguments.
- **Use case:** Quick health check.

## `get system interface`

```text
get system interface
```

- **Purpose:** List interface status and addressing.
- **Arguments:** No arguments.
- **Use case:** Find an interface IP.

## `get router info routing-table all`

```text
get router info routing-table all
```

- **Purpose:** Display the routing table.
- **Arguments:** all: show routes across protocols.
- **Use case:** Validate the next hop for a destination.

> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
