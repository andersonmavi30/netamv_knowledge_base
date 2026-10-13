---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Huawei VRP

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** VRP (check device release). Verify against your device.

## `display lldp neighbor brief`

```text
display lldp neighbor brief
```

- **Purpose:** List LLDP neighbors.
- **Parameters:** brief: summary
- **Filter / lookup:** `display lldp neighbor brief | include GigabitEthernet`

## `display vlan`

```text
display vlan
```

- **Purpose:** Show VLAN information.
- **Parameters:** No options
- **Filter / lookup:** `display vlan | include 10`

## `display mac-address`

```text
display mac-address
```

- **Purpose:** Inspect MAC address table.
- **Parameters:** No options
- **Filter / lookup:** `display mac-address | include 0011-2233-4455`

## `display stp brief`

```text
display stp brief
```

- **Purpose:** Summarize STP state.
- **Parameters:** brief: short output
- **Filter / lookup:** `display stp brief | include DISCARDING`

## `display ip routing-table 198.51.100.10`

```text
display ip routing-table 198.51.100.10
```

- **Purpose:** Look up destination routing.
- **Parameters:** IP: destination
- **Filter / lookup:** `display ip routing-table | include 198.51.100`

> Examples pending lab validation. Confirm the release and syntax with CLI help.
