---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Dell OS6

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Port descriptions

See the command in the [interface guide](03-interfaces.md).

## LACP port status

```text
show lacp interfaces
```

- **Purpose:** LACP port status.
- **Options and filters:** interfaces: LACP member information
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## PoE consumption

```text
show power inline
```

- **Purpose:** PoE consumption.
- **Options and filters:** inline: PoE interface power
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Switch system health

```text
show system
```

- **Purpose:** Switch system health.
- **Options and filters:** system: hardware summary
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Management SVI status

```text
show ip interface brief | include vlan
```

- **Purpose:** Management SVI status.
- **Options and filters:** brief: IPv4 summary; L3 platforms
- **Operational example:** Find relevant information while investigating an issue without reading all output.

