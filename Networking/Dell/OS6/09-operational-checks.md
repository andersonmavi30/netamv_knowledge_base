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

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
