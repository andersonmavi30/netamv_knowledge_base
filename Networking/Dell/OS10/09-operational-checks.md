---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Additional operational checks — Dell OS10

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** SmartFabric OS10, platform-specific. Confirm commands and options with the installed CLI help.

## LLDP neighbors

```text
show lldp neighbors | grep UPLINK
```

- **Purpose:** Discover attached network devices.
- **Parameters / flags:** neighbors: LLDP list.
- **Operational use:** Identify uplink peer.
- **Filter / verification:** `show lldp neighbors`

## LAG member states

```text
show port-channel summary | grep Po
```

- **Purpose:** Inspect LAG health where supported.
- **Parameters / flags:** summary: member overview.
- **Operational use:** Diagnose missing aggregated link.
- **Filter / verification:** `show port-channel summary`

## OSPF adjacency states

```text
show ip ospf neighbor | grep FULL
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
show ip bgp summary | grep Idle
```

- **Purpose:** Review BGP sessions on BGP-enabled switches.
- **Parameters / flags:** summary: BGP peer table.
- **Operational use:** Find peer stuck in Active.
- **Filter / verification:** `show ip bgp summary | grep Active`

## `show lldp neighbors interface ethernet 1/1/1 detail`

```text
show lldp neighbors interface ethernet 1/1/1 detail
```

- **Purpose:** Read all LLDP TLVs advertised by the neighbor on Ethernet 1/1/1.
- **Arguments:** interface ethernet 1/1/1: filter to a local interface; detail: expanded neighbor information.
- **Use case:** Identify the peer switch, remote port, management IP and capabilities during cabling troubleshooting.
- **Official reference:** https://www.dell.com/support/manuals/en-us/smartfabric-os10-emp-partner/smartfabric-os-user-guide-10-6-1-x/show-lldp-neighbors?guid=guid-cf4a7765-02fd-4278-9bcb-c49088ba61e5&lang=en-us

## `show inventory | grep -i Serial`

```text
show inventory | grep -i Serial
```

- **Purpose:** Find serial-number fields in the OS10 hardware inventory.
- **Arguments:** show inventory: chassis/modules; | grep -i Serial: case-insensitive output filter.
- **Use case:** Collect inventory identifiers before opening a Dell hardware support case.
- **Reference:** https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-3/show-inventory?guid=guid-08e4f141-ddea-4d66-999b-c84edd73eff4&lang=en-us

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://www.dell.com/support/home/en-us/products/networking)

## Port channel overview

```text
show port-channel summary
```

- **Purpose:** Show port-channel membership and operational aggregation state.
- **Parameters / flags:** summary: condensed LAG view; relevant when port channels are configured.
- **Operational use:** Verify bundled links before troubleshooting LACP forwarding.
- **Reference:** https://www.dell.com/support/home/en-us/products/networking

## OS10 software release

```text
show version
```

- **Purpose:** Read system software version and platform details.
- **Parameters / flags:** version: software release and hardware summary.
- **Operational use:** Confirm release before troubleshooting a release-dependent feature.

## IPv4 routing table

```text
show ip route
```

- **Purpose:** Display installed IPv4 routes and next hops.
- **Parameters / flags:** ip route: IPv4 unicast routes; route codes identify source.
- **Operational use:** Confirm that a next-hop route exists before testing forwarding.
- **Validation:** Not lab-verified; check version and privileges.

## Detailed Ethernet interface state

```text
show interface ethernet 1/1/1
```

- **Purpose:** Inspect the operational state and counters of Ethernet 1/1/1.
- **Parameters / flags:** ethernet 1/1/1: selected front-panel port; replace with installed port number.
- **Operational use:** Investigate a single failing uplink without dumping all ports.
- **Validation:** Not lab verified; confirm release and CLI context.
