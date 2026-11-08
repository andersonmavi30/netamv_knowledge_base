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

## Neighbor and VLAN forwarding lookup

### `show lldp neighbor-info detail`

```text
show lldp neighbor-info detail
```

- **Purpose:** Display detailed LLDP neighbor identification and capabilities.
- **Arguments:** detail: extended neighbor TLVs; LLDP must be enabled.
- **Use case:** Verify operational state without changing configuration.

### `show mac-address-table vlan 10`

```text
show mac-address-table vlan 10
```

- **Purpose:** List MAC entries learned in VLAN 10.
- **Arguments:** vlan 10: scope the lookup to VLAN ID 10.
- **Use case:** Verify operational state without changing configuration.

> Not lab-verified. AOS-CX 10.x; model/release support varies.

**Reference:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf

## Multicast and spanning-tree verification

### `show ip igmp snooping`

```text
show ip igmp snooping
```

- **Purpose:** Inspect configured and operational IGMP snooping state.
- **Arguments:** igmp snooping: multicast group management; requires corresponding feature.
- **Use case:** Investigate incidents without changing configuration.

### `show spanning-tree detail`

```text
show spanning-tree detail
```

- **Purpose:** Inspect expanded spanning-tree port and bridge state.
- **Arguments:** detail: expanded STP view; requires STP enabled; support varies by release.
- **Use case:** Investigate incidents without changing configuration.

> Not lab-verified. AOS-CX 10.x; model/release support varies.

**Reference:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf
