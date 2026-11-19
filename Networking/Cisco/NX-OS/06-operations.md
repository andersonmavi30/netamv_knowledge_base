---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Layer 2 operations

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ NX-OS](README.md)

**Platform:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); verify syntax by model and release.

## `show vlan brief`

```text
show vlan brief
```

- **Purpose:** List configured VLANs and associated switchport membership.
- **Arguments:** `vlan brief`: condensed VLAN names, status and ports; read-only.
- **Use case:** Confirm a VLAN exists before troubleshooting an access port.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified.

## `show port-channel summary`

```text
show port-channel summary
```

- **Purpose:** Summarize port-channel bundles, protocol and member interface status.
- **Arguments:** `port-channel summary`: aggregated links and member status; port-channel must be configured.
- **Use case:** Identify an LACP member that is not bundled.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified.
