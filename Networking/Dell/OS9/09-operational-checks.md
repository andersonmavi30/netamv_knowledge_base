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

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://www.dell.com/support/home/en-us/products/networking)
