---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# System and hardware

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ NX-OS](README.md)

**Platform:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); verify syntax by model and release.

## `show version`

```text
show version
```

- **Purpose:** Identify NX-OS release, uptime and Nexus hardware platform.
- **Arguments:** No flags: `show version` displays platform and software information; read-only.
- **Use case:** Confirm switch release before troubleshooting a feature.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified.

## `show module`

```text
show module
```

- **Purpose:** Display Nexus hardware modules and their operational states.
- **Arguments:** `module`: chassis module inventory and status; information varies by model.
- **Use case:** Confirm whether a line card or supervisor is healthy.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified.
