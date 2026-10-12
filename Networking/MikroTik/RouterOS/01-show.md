---
tags: [cli, mikrotik, routeros, show]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🔎 Show and status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ MikroTik](../README.md)

**Platform:** MikroTik / RouterOS · **Reference version:** 7.x.

## `/system resource print`

```text
/system resource print
```

- **Purpose:** Device resource and software summary.
- **Parameters/filters:** print: show current properties.
- **Operational example:** Check CPU load and RouterOS version.

## `/system identity print`

```text
/system identity print
```

- **Purpose:** Show the router name.
- **Parameters/filters:** identity: hostname menu.
- **Operational example:** Identify the router before changes.

## `/interface print where name~"ether"`

```text
/interface print where name~"ether"
```

- **Purpose:** List Ethernet interfaces only.
- **Parameters/filters:** where: filter; ~: regex match on name.
- **Operational example:** Find ether1/ether2 quickly.

## `/ip address print where interface="ether2"`

```text
/ip address print where interface="ether2"
```

- **Purpose:** Find addresses on ether2.
- **Parameters/filters:** where: exact property equality.
- **Operational example:** Confirm local LAN IP.

## `/ip route print where dst-address="0.0.0.0/0"`

```text
/ip route print where dst-address="0.0.0.0/0"
```

- **Purpose:** Show default routes.
- **Parameters/filters:** dst-address: exact prefix.
- **Operational example:** Review main Internet gateway.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
