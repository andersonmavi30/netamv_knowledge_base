---
tags: [cli, huawei, vrp, configuration]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# ⚙️ General configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Huawei](../README.md)

**Platform:** Huawei / VRP · **Reference version:** VRP (generic; confirm your device's release).

## `system-view`

```text
system-view
sysname HW-LAB
return
```

- **Purpose:** Change system name.
- **Parameters/filters:** system-view: configuration; sysname: hostname; return: user view.
- **Operational example:** Label a Huawei lab switch.

## `system-view`

```text
system-view
vlan 10
 quit
interface GigabitEthernet0/0/1
 port link-type access
 port default vlan 10
 quit
return
```

- **Purpose:** Assign an access port to VLAN 10.
- **Parameters/filters:** port link-type access: L2 access; port default vlan 10: PVID.
- **Operational example:** Attach a lab workstation to VLAN 10.
- **Caution:** Check existing trunk/port role; may interrupt traffic.

## `system-view`

```text
system-view
ip route-static 198.51.100.0 255.255.255.0 192.0.2.254
return
```

- **Purpose:** Create an IPv4 static route on L3-capable devices.
- **Parameters/filters:** prefix/mask: network; next-hop: reachable router.
- **Operational example:** Reach a remote lab subnet.
- **Caution:** Needs L3 support and reachable next hop.

## `display current-configuration | include sysname`

```text
display current-configuration | include sysname
```

- **Purpose:** Verify the hostname after change.
- **Parameters/filters:** include: find relevant line.
- **Operational example:** Confirm HW-LAB.

## `save`

```text
save
```

- **Purpose:** Save running configuration for reboot persistence.
- **Parameters/filters:** Interactive confirmation may be required.
- **Operational example:** Persist tested lab changes.
- **Caution:** Only save after review; VRP versions with candidate configs may require commit first.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
