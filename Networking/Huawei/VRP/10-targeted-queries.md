---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Huawei VRP

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Interface descriptions

```text
display interface description | include UPLINK
```

- **Purpose:** Interface descriptions.
- **Options and filters:** description: port labels
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## NTP clock state

```text
display ntp-service status
```

- **Purpose:** NTP clock state.
- **Options and filters:** status: synchronization
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## OSPF-enabled interfaces

```text
display ospf interface | include GigabitEthernet
```

- **Purpose:** OSPF-enabled interfaces.
- **Options and filters:** interface: participating ports
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Eth-Trunk member state

```text
display eth-trunk 1
```

- **Purpose:** Eth-Trunk member state.
- **Options and filters:** 1: trunk index
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Optical transceiver diagnostics

```text
display transceiver interface GigabitEthernet0/0/1 verbose
```

- **Purpose:** Optical transceiver diagnostics.
- **Options and filters:** verbose: expanded optics; release-dependent
- **Operational example:** Find relevant information while investigating an issue without reading all output.

