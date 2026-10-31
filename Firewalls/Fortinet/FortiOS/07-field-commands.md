---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Fortinet FortiOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** FortiOS 7.x. Verify against your device.

## `get system ha status`

```text
get system ha status | grep -i mode
```

- **Purpose:** Inspect HA cluster state.
- **Parameters:** No flags
- **Filter / lookup:** `get system ha status | grep -i mode`




## `show firewall address`

```text
show firewall address | grep -f LAB-NET
```

- **Purpose:** Inspect address objects.
- **Parameters:** No flags
- **Filter / lookup:** `show firewall address | grep -f LAB-NET`

## `diagnose sys sdwan member 1`

```text
diagnose sys sdwan member 1
```

- **Purpose:** Show details for SD-WAN member sequence 1 without dumping all members.
- **Arguments:** member 1: select SD-WAN member sequence ID 1; the ID is configuration-dependent.
- **Use case:** Investigate which WAN member is configured and how it behaves during an ISP incident.
- **Filter / lookup:** The member ID is the built-in lookup; no pipe is required.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.7/cli-reference/235530229/diagnose-sys

> Examples pending lab validation. Confirm the release and syntax with CLI help.
