---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Huawei VRP

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** VRP (check device release). Verify against your device.

## `display lldp neighbor brief`

```text
display lldp neighbor brief | include GigabitEthernet
```

- **Purpose:** List LLDP neighbors.
- **Parameters:** brief: summary
- **Filter / lookup:** `display lldp neighbor brief | include GigabitEthernet`

## `display vlan`

```text
display vlan | include 10
```

- **Purpose:** Show VLAN information.
- **Parameters:** No options
- **Filter / lookup:** `display vlan | include 10`

## `display mac-address`

```text
display mac-address | include 0011-2233-4455
```

- **Purpose:** Inspect MAC address table.
- **Parameters:** No options
- **Filter / lookup:** `display mac-address | include 0011-2233-4455`

## `display stp brief`

```text
display stp brief | include DISCARDING
```

- **Purpose:** Summarize STP state.
- **Parameters:** brief: short output
- **Filter / lookup:** `display stp brief | include DISCARDING`

## `display lldp local interface GigabitEthernet 0/0/1`

```text
display lldp local interface GigabitEthernet 0/0/1
```

- **Purpose:** Inspect the local LLDP information being advertised on an individual interface.
- **Parameters / flags:** local: local device LLDP information; interface: target port; GigabitEthernet 0/0/1: example interface.
- **Operational use:** Check LLDP operation and advertisements when a neighboring switch cannot discover this uplink.
- **Official reference:** https://info.support.huawei.com/network/ptmngsys/Web/tsrev_s/en/content/s/38_edesk_lldp_neighbors_failing/edesk_lldp_neighbors_failing_edesk002.html

> Examples pending lab validation. Confirm the release and syntax with CLI help.
