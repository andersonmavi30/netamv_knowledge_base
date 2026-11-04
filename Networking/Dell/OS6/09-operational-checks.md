---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Additional operational checks — Dell OS6

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 — N-series, release-specific. Confirm commands and options with the installed CLI help.

## LLDP neighbors

```text
show lldp neighbors | include UPLINK
```

- **Purpose:** Show neighboring network devices.
- **Parameters / flags:** neighbors: LLDP entries.
- **Operational use:** Identify cable neighbor.
- **Filter / verification:** `show lldp neighbors`

## IPv4 ARP mappings

```text
show ip arp | include 192.0.2
```

- **Purpose:** Show IP-to-MAC entries when L3 is enabled.
- **Parameters / flags:** No flags; L3 support required.
- **Operational use:** Look up gateway MAC.
- **Filter / verification:** `show ip arp`

## MST status

```text
show spanning-tree mst | include 10
```

- **Purpose:** Inspect MST spanning-tree information.
- **Parameters / flags:** mst: multiple spanning tree.
- **Operational use:** Investigate blocked links.
- **Filter / verification:** `show spanning-tree mst`

## Switchport details

```text
show interfaces switchport gigabitethernet 1/0/1
```

- **Purpose:** Inspect allowed VLANs and access/trunk settings.
- **Parameters / flags:** Port ID varies by hardware.
- **Operational use:** Check a VLAN mismatch.
- **Filter / verification:** `show interfaces switchport gigabitethernet 1/0/1`

## DHCP snooping binding table

```text
show ip dhcp snooping binding | include 192.0.2
```

- **Purpose:** Inspect DHCP snooping bindings where enabled.
- **Parameters / flags:** binding: learned DHCP associations.
- **Operational use:** Investigate a blocked DHCP client.
- **Filter / verification:** `show ip dhcp snooping binding`

## `show mac address-table | include 0011`

```text
show mac address-table | include 0011
```

- **Purpose:** Search dynamically learned MAC table entries for a particular MAC prefix.
- **Parameters / flags:** show mac address-table: bridging table; | include 0011: show matching lines on releases supporting output filters.
- **Operational use:** Locate a connected endpoint by the first hexadecimal digits of its MAC address.
- **Official reference:** https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf

## `show lldp local-device detail Gi1/0/1`

```text
show lldp local-device detail Gi1/0/1
```

- **Purpose:** Inspect LLDP information advertised locally on a specific OS6 switchport.
- **Parameters:** detail: expanded LLDP data; Gi1/0/1: selected physical port.
- **Use case:** Check what chassis/port identification the switch advertises to neighbors.
- **Reference:** https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)

## Switchport operational status

```text
show interfaces status
```

- **Purpose:** Display switchport link status and related port attributes.
- **Parameters / flags:** status: concise port table; supported interfaces depend on N-series model.
- **Operational use:** Find disconnected or unexpected port speeds on an OS6 switch.
- **Reference:** https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf

## Switch firmware version

```text
show version
```

- **Purpose:** Read OS6 software release and hardware identification.
- **Parameters / flags:** version: software and platform summary; output depends on model.
- **Operational use:** Record the version before checking a model-specific command.

## Switchport mode and VLANs

```text
show interfaces switchport
```

- **Purpose:** Inspect switchport mode and VLAN membership on OS6.
- **Parameters / flags:** switchport: L2 switchport details; syntax may vary by firmware.
- **Operational use:** Check unexpected access/trunk VLAN assignment.
- **Validation:** Not lab-verified; check version and privileges.
