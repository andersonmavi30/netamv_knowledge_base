---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Fortinet FortiOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** FortiOS 7.x. Verify against your device.

## `get system ha status`

```text
get system ha status
```

- **Purpose:** Inspect HA cluster state.
- **Parameters:** No flags
- **Filter / lookup:** `get system ha status | grep -i mode`

## `diagnose sys session stat`

```text
diagnose sys session stat
```

- **Purpose:** Inspect session statistics.
- **Parameters:** stat: session counts
- **Filter / lookup:** `diagnose sys session stat | grep -i session`

## `diagnose vpn ike gateway list`

```text
diagnose vpn ike gateway list
```

- **Purpose:** Inspect IKE gateways.
- **Parameters:** list: gateways
- **Filter / lookup:** `diagnose vpn ike gateway list | grep -i name=`

## `get router info routing-table all`

```text
get router info routing-table all
```

- **Purpose:** Inspect current routes.
- **Parameters:** all: full routing table
- **Filter / lookup:** `get router info routing-table all | grep 198.51.100`

## `show firewall address`

```text
show firewall address
```

- **Purpose:** Inspect address objects.
- **Parameters:** No flags
- **Filter / lookup:** `show firewall address | grep -f LAB-NET`

> Examples pending lab validation. Confirm the release and syntax with CLI help.
