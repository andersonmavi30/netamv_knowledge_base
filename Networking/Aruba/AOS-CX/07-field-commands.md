---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Field checks

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify model and release.

## `show lacp aggregates | include lag1`

```text
show lacp aggregates | include lag1
```

- **Purpose:** Inspect LACP aggregation.
- **Arguments:** include: lag name.
- **Use case:** Diagnose LAG.

## `show ntp associations | include 192.0.2`

```text
show ntp associations | include 192.0.2
```

- **Purpose:** Find NTP associations.
- **Arguments:** include: IP pattern.
- **Use case:** Check time peers.

## `show interface 1/1/4 | include error`

```text
show interface 1/1/4 | include error
```

- **Purpose:** Inspect port errors.
- **Arguments:** include: error keyword.
- **Use case:** Find physical issues.

## `show ip route | include 203.0.113`

```text
show ip route | include 203.0.113
```

- **Purpose:** Find a routed prefix.
- **Arguments:** include: prefix match.
- **Use case:** Check route.

> Lab validation required. Mirror/tshark need platform support and authorization; disable after use.

## LACP and OSPF neighbors

### `show lacp interfaces`

```text
show lacp interfaces
```

- **Purpose:** Review LACP member interface operational states.
- **Arguments:** interfaces: per-member LACP state; requires configured LAG.
- **Use case:** Verify operational state without changing configuration.

### `show ip ospf neighbors all-vrfs`

```text
show ip ospf neighbors all-vrfs
```

- **Purpose:** Inspect OSPF adjacency states across VRFs.
- **Arguments:** all-vrfs: include all routing contexts; requires OSPF feature.
- **Use case:** Verify operational state without changing configuration.

> Not lab-verified. AOS-CX 10.x; model/release support varies.

**Reference:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf

## EVPN peers and VXLAN tunnels

### `show bgp l2vpn evpn summary`

```text
show bgp l2vpn evpn summary
```

- **Purpose:** Display EVPN BGP neighbor states.
- **Arguments:** l2vpn evpn: EVPN address family; summary: neighbor states; requires EVPN.
- **Use case:** Verify status before a network change.

### `show interface vxlan vteps`

```text
show interface vxlan vteps
```

- **Purpose:** Inspect remote VTEP peers and VXLAN tunnel reachability.
- **Arguments:** vteps: VXLAN peer endpoint view; supported EVPN/VXLAN platforms only.
- **Use case:** Verify status before a network change.

> Not lab-verified. AOS-CX 10.x; model/release support varies.

**Reference:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf

## VSX and VSF topology

### `show vsx status`

```text
show vsx status
```

- **Purpose:** Inspect multi-chassis VSX role and inter-switch state.
- **Arguments:** vsx status: VSX peer and role data; only on VSX-capable switches.
- **Use case:** Verify status before a network change.

### `show vsf`

```text
show vsf
```

- **Purpose:** Inspect VSF stack membership and status.
- **Arguments:** vsf: Virtual Switching Framework status; only on supported switch families.
- **Use case:** Verify status before a network change.

> Not lab-verified. AOS-CX 10.x; model/release support varies.

**Reference:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf
