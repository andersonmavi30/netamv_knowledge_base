---
tags: [cli, mikrotik, routeros, filters]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🔍 Operational filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ MikroTik](../README.md)

**Platform:** MikroTik / RouterOS · **Reference version:** 7.x.


## `/ip route print where dst-address="198.51.100.0/24"`

```text
/ip route print where dst-address="198.51.100.0/24"
```

- **Purpose:** Find one route prefix.
- **Parameters/filters:** where: property filter; =: exact match.
- **Operational example:** Inspect the lab destination route.

## `/ip firewall filter print stats where chain="forward"`

```text
/ip firewall filter print stats where chain="forward"
```

- **Purpose:** Show forwarding rules with counters.
- **Parameters/filters:** stats: counters; where: restrict chain.
- **Operational example:** Check if traffic hits a firewall rule.

## `/ip firewall address-list print where list="LAB-HOSTS"`

```text
/ip firewall address-list print where list="LAB-HOSTS"
```

- **Purpose:** List members of one address list.
- **Parameters/filters:** list=: exact list name.
- **Operational example:** Inspect lab hosts before changes.

## `/log print where message~"login"`

```text
/log print where message~"login"
```

- **Purpose:** Search login-related log messages.
- **Parameters/filters:** message~: regex on message.
- **Operational example:** Review recent administrative access.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
