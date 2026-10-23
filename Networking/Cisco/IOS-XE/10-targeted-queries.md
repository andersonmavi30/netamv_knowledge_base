---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Cisco IOS-XE

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Aggregated link status

```text
show etherchannel summary | include Po
```

- **Purpose:** Aggregated link status.
- **Options and filters:** summary: bundle membership; switching only
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## CEF source-destination path

```text
show ip cef exact-route 192.0.2.10 198.51.100.10
```

- **Purpose:** CEF source-destination path.
- **Options and filters:** exact-route: selected forwarding path
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Hardware temperature and power

```text
show environment all | include Temperature|Power
```

- **Purpose:** Hardware temperature and power.
- **Options and filters:** all: all sensors, platform-specific
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## OSPF external LSAs

```text
show ip ospf database external | include Link State ID
```

- **Purpose:** OSPF external LSAs.
- **Options and filters:** external: type-5 LSAs
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## DHCP snooping security bindings

```text
show ip dhcp snooping binding | include 192.0.2
```

- **Purpose:** DHCP snooping security bindings.
- **Options and filters:** binding: learned trusted leases
- **Operational example:** Find relevant information while investigating an issue without reading all output.

