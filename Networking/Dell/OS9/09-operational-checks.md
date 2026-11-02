---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Additional operational checks — Dell OS9

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** OS9 / Force10, platform-specific. Confirm commands and options with the installed CLI help.

## LLDP neighbors

```text
show lldp neighbors | grep UPLINK
```

- **Purpose:** Discover neighboring devices.
- **Parameters / flags:** neighbors: LLDP entries.
- **Operational use:** Validate a physical connection.
- **Filter / verification:** `show lldp neighbors`

## LAG summary

```text
show port-channel summary | grep Po
```

- **Purpose:** Check link aggregation member state where available.
- **Parameters / flags:** summary: condensed group/member status.
- **Operational use:** Find a suspended bundle member.
- **Filter / verification:** `show port-channel summary`

## BGP peer overview

```text
show ip bgp summary | grep Idle
```

- **Purpose:** Inspect BGP session states on L3 devices.
- **Parameters / flags:** summary: brief peers.
- **Operational use:** Locate Idle peer.
- **Filter / verification:** `show ip bgp summary | grep Idle`

## MAC address learning

```text
show mac-address-table | grep 0011
```

- **Purpose:** View learned L2 MAC addresses on supported hardware.
- **Parameters / flags:** No flags; syntax may differ by train.
- **Operational use:** Identify MAC on a trunk.
- **Filter / verification:** `show mac-address-table`

## OSPF neighbors

```text
show ip ospf neighbor | grep FULL
```

- **Purpose:** Display active OSPF adjacencies.
- **Parameters / flags:** No flags; requires OSPF.
- **Operational use:** Check neighbor health.
- **Filter / verification:** `show ip ospf neighbor`

## `show processes cpu summary`

```text
show processes cpu summary
```

- **Purpose:** Display a summary of CPU use by control-plane processes on supporting Force10 OS9 hardware.
- **Parameters / flags:** processes cpu: CPU monitoring; summary: compact process/stack-unit statistics (platform-dependent).
- **Operational use:** Confirm control-plane load before enabling an expensive debug session.
- **Official reference:** https://www.dell.com/support/manuals/en-us/dell-emc-os-9/s6010-on-9.14.2.4-cli/show-processes-cpu?guid=guid-9e687ea4-6b17-485c-aded-809d15df998f&lang=en-us

## `show ip bgp neighbors 192.0.2.1 | grep "BGP state"`

```text
show ip bgp neighbors 192.0.2.1 | grep "BGP state"
```

- **Purpose:** Check the BGP FSM state for one configured neighbor.
- **Parameters:** 192.0.2.1: neighbor IP; | grep: select its BGP state field.
- **Use case:** Identify why a routing peer has not reached Established.
- **Reference:** https://www.dell.com/support/manuals/en-za/dell-emc-smartfabric-os10/techsheet-os10-5-3-0-os9-pub/border-gateway-protocol?guid=guid-8520ae6f-95e0-411e-986f-978c419f8d0f&lang=en-us

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://www.dell.com/support/home/en-us/products/networking)
