---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Routing protocols

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ NX-OS](README.md)

**Platform:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); verify syntax by model and release.

## `show ip route summary`

```text
show ip route summary
```

- **Purpose:** Display a summary of installed IPv4 routes and their source protocols.
- **Arguments:** `ip route summary`: summarized unicast routing table; routing context/VRF can affect output.
- **Use case:** Compare route counts before and after an approved routing change.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified; verify options on your release.
