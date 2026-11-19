---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Interfaces and counters

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ NX-OS](README.md)

**Platform:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); verify syntax by model and release.

## `show interface status`

```text
show interface status
```

- **Purpose:** Summarize interface state, VLAN assignment, duplex, speed and media type.
- **Arguments:** `interface status`: concise port overview, without interface changes.
- **Use case:** Find down uplinks or ports negotiated at an unexpected speed.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified.
