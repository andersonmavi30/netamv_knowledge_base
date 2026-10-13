---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — MikroTik RouterOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** RouterOS 7.x. Verify against your device.

## `/interface ethernet print detail where name="ether1"`

```text
/interface ethernet print detail where name="ether1"
```

- **Purpose:** Inspect interface details.
- **Parameters:** detail: expanded; where: filter
- **Filter / lookup:** `/interface print where name="ether1"`

## `/ip dhcp-client print detail`

```text
/ip dhcp-client print detail
```

- **Purpose:** Inspect DHCP clients.
- **Parameters:** detail: all details
- **Filter / lookup:** `/ip dhcp-client print where interface="ether1"`

## `/ip firewall nat print stats where chain="srcnat"`

```text
/ip firewall nat print stats where chain="srcnat"
```

- **Purpose:** Show source NAT counters.
- **Parameters:** stats: counters; where: filter
- **Filter / lookup:** `/ip firewall nat print where action="masquerade"`

## `/ip firewall filter print where action="drop"`

```text
/ip firewall filter print where action="drop"
```

- **Purpose:** List drop rules.
- **Parameters:** where: filter on action
- **Filter / lookup:** `/ip firewall filter print stats where action="drop"`

## `/ip neighbor print detail`

```text
/ip neighbor print detail
```

- **Purpose:** Inspect discovered neighbors.
- **Parameters:** detail: expanded info
- **Filter / lookup:** `/ip neighbor print where interface="ether2"`

## `/routing route print where dst-address="0.0.0.0/0"`

```text
/routing route print where dst-address="0.0.0.0/0"
```

- **Purpose:** Inspect default route candidates.
- **Parameters:** where: exact prefix
- **Filter / lookup:** `/ip route print where dst-address="0.0.0.0/0"`

> Examples pending lab validation. Confirm the release and syntax with CLI help.
