---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Cisco IOS

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Uplink descriptions

```text
show interfaces description | include UPLINK
```

- **Purpose:** Uplink descriptions.
- **Options and filters:** description: interface label summary
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## OSPF router LSAs

```text
show ip ospf database router | include Link State ID
```

- **Purpose:** OSPF router LSAs.
- **Options and filters:** database router: router LSAs
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## NAT translation counters

```text
show ip nat statistics | include Hits|Misses
```

- **Purpose:** NAT translation counters.
- **Options and filters:** statistics: totals and hits
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Memory resource health

```text
show memory statistics | include Processor
```

- **Purpose:** Memory resource health.
- **Options and filters:** statistics: memory usage
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Ethernet PHY counters

```text
show controllers ethernet-controller GigabitEthernet0/0 | include error
```

- **Purpose:** Ethernet PHY counters.
- **Options and filters:** controller: hardware counters; platform-dependent
- **Operational example:** Find relevant information while investigating an issue without reading all output.

