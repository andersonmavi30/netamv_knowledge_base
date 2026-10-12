---
tags: [cli, mikrotik, routeros, interfaces]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🔌 Interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ MikroTik](../README.md)

**Platform:** MikroTik / RouterOS · **Reference version:** 7.x.

## `/interface print where name="ether2"`

```text
/interface print where name="ether2"
```

- **Purpose:** Check an exact interface state.
- **Parameters/filters:** where name=: interface selection.
- **Operational example:** Inspect the LAN port.

## `/ip address add address=192.0.2.1/24 interface=ether2 comment="LAB-LAN"`

```text
/ip address add address=192.0.2.1/24 interface=ether2 comment="LAB-LAN"
```

- **Purpose:** Assign an IPv4 address to an interface.
- **Parameters/filters:** add: new entry; address: IP/prefix; interface: port.
- **Operational example:** Give ether2 a lab LAN IP.
- **Caution:** Changes traffic immediately; use Safe Mode for remote work.

## `/ip address print detail where interface="ether2"`

```text
/ip address print detail where interface="ether2"
```

- **Purpose:** Verify detailed IP properties on ether2.
- **Parameters/filters:** detail: more fields; where: limit interface.
- **Operational example:** Confirm address and network.

## `/interface set [find name="ether2"] comment="LAB-LAN"`

```text
/interface set [find name="ether2"] comment="LAB-LAN"
```

- **Purpose:** Set an interface description.
- **Parameters/filters:** find: locate interface by name; set: update.
- **Operational example:** Label a LAN port for future troubleshooting.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
