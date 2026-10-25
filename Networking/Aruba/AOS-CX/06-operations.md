---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Operations

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify model and release.

## `show lldp neighbor-info | include 1/1/1`

```text
show lldp neighbor-info | include 1/1/1
```

- **Purpose:** Find a port's LLDP neighbor.
- **Arguments:** include: port filter.
- **Use case:** Identify attached switch.

## `show mac-address-table | include 1/1/2`

```text
show mac-address-table | include 1/1/2
```

- **Purpose:** Find learned MACs on a port.
- **Arguments:** include: port match.
- **Use case:** Locate a host.

## `show ntp status`

```text
show ntp status
```

- **Purpose:** Check NTP clock status.
- **Arguments:** status: scoped NTP query.
- **Use case:** Correlate log times.

## `show spanning-tree | include Root`

```text
show spanning-tree | include Root
```

- **Purpose:** Locate STP root lines.
- **Arguments:** include: text match.
- **Use case:** Investigate STP topology.

> Lab validation required. Mirror/tshark need platform support and authorization; disable after use.
