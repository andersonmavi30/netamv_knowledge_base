---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — MikroTik RouterOS

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Raw firewall counters

```text
/ip firewall raw print stats where chain="prerouting"
```

- **Purpose:** Raw firewall counters.
- **Options and filters:** stats: packets and bytes; where: chain
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Established OSPF neighbors

```text
/routing ospf neighbor print where state="Full"
```

- **Purpose:** Established OSPF neighbors.
- **Options and filters:** where: exact neighbor state
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Bridge VLAN membership

```text
/interface bridge vlan print where vlan-ids=10
```

- **Purpose:** Bridge VLAN membership.
- **Options and filters:** vlan-ids: configured VLAN ID
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## DNS cache lookups

```text
/ip dns cache print where name~"example"
```

- **Purpose:** DNS cache lookups.
- **Options and filters:** ~: regex on name
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## NTP client synchronization

```text
/system ntp client print
```

- **Purpose:** NTP client synchronization.
- **Options and filters:** print: client state
- **Operational example:** Find relevant information while investigating an issue without reading all output.

