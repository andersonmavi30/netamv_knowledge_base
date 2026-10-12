---
tags: [cli, mikrotik, routeros, configuration]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# ⚙️ General configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ MikroTik](../README.md)

**Platform:** MikroTik / RouterOS · **Reference version:** 7.x.

## `/system identity set name=MT-LAB`

```text
/system identity set name=MT-LAB
```

- **Purpose:** Set hostname.
- **Parameters/filters:** set name=: assign router identity.
- **Operational example:** Label a lab router.

## `/ip route add dst-address=198.51.100.0/24 gateway=192.0.2.254 comment="LAB"`

```text
/ip route add dst-address=198.51.100.0/24 gateway=192.0.2.254 comment="LAB"
```

- **Purpose:** Add a static route.
- **Parameters/filters:** dst-address: prefix; gateway: next hop.
- **Operational example:** Route traffic to a lab network.
- **Caution:** Check next hop and policy routing before applying.

## `/ip firewall address-list add list=LAB-HOSTS address=192.0.2.10 comment="LAB"`

```text
/ip firewall address-list add list=LAB-HOSTS address=192.0.2.10 comment="LAB"
```

- **Purpose:** Add a host to an address list.
- **Parameters/filters:** list: group; address: member IP; comment: label.
- **Operational example:** Manage lab destinations by group.

## `/ip route print where dst-address="198.51.100.0/24"`

```text
/ip route print where dst-address="198.51.100.0/24"
```

- **Purpose:** Verify the new route.
- **Parameters/filters:** where: select exact prefix.
- **Operational example:** Check gateway and active flags.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
