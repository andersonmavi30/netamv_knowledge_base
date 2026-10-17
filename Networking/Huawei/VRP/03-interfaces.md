---
tags: [cli, huawei, vrp, interfaces]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# 🔌 Interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Huawei](../README.md)

**Platform:** Huawei / VRP · **Reference version:** VRP (generic; confirm your device's release).


## `system-view`

```text
system-view
interface GigabitEthernet0/0/1
 description LAB-UPLINK
 undo shutdown
 quit
return
```

- **Purpose:** Label and enable an Ethernet port.
- **Parameters/filters:** system-view: config; undo shutdown: enable; quit: leave interface; return: user view.
- **Operational example:** Activate a lab uplink.
- **Caution:** Changes link state; port roles may vary by VRP family.

## `system-view`

```text
system-view
vlan 10
 quit
interface Vlanif10
 ip address 192.0.2.1 255.255.255.0
 quit
return
```

- **Purpose:** Create VLAN 10 and an L3 SVI where supported.
- **Parameters/filters:** Vlanif10: VLAN interface; ip address: IPv4/netmask.
- **Operational example:** Manage a lab switch over VLAN 10.
- **Caution:** Some devices require VLAN, switching and L3 prerequisites.

## `display ip interface brief | include Vlanif10`

```text
display ip interface brief | include Vlanif10
```

- **Purpose:** Verify the SVI address and status.
- **Parameters/filters:** | include: show matching lines.
- **Operational example:** Confirm 192.0.2.1/24.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
