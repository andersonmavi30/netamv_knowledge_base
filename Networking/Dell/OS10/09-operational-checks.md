---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Additional operational checks — Dell OS10

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** SmartFabric OS10, platform-specific. Confirm commands and options with the installed CLI help.

## LLDP neighbors

```text
show lldp neighbors
```

- **Purpose:** Discover attached network devices.
- **Parameters / flags:** neighbors: LLDP list.
- **Operational use:** Identify uplink peer.
- **Filter / verification:** `show lldp neighbors`

## LAG member states

```text
show port-channel summary
```

- **Purpose:** Inspect LAG health where supported.
- **Parameters / flags:** summary: member overview.
- **Operational use:** Diagnose missing aggregated link.
- **Filter / verification:** `show port-channel summary`

## OSPF adjacency states

```text
show ip ospf neighbor
```

- **Purpose:** Inspect OSPF neighbor state.
- **Parameters / flags:** No flags; requires routing configuration.
- **Operational use:** Find a neighbor not Full.
- **Filter / verification:** `show ip ospf neighbor`

## Transceiver diagnostics

```text
show interface ethernet 1/1/1 transceiver
```

- **Purpose:** View optical module data on a supported OS10 platform.
- **Parameters / flags:** ethernet: physical port; transceiver: optics information.
- **Operational use:** Check a suspected bad optic.
- **Filter / verification:** `show interface ethernet 1/1/1 transceiver`

## BGP peer summary

```text
show ip bgp summary
```

- **Purpose:** Review BGP sessions on BGP-enabled switches.
- **Parameters / flags:** summary: BGP peer table.
- **Operational use:** Find peer stuck in Active.
- **Filter / verification:** `show ip bgp summary | grep Active`

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://www.dell.com/support/home/en-us/products/networking)
