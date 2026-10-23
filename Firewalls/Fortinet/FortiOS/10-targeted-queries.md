---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Fortinet FortiOS

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## SD-WAN service steering

```text
diagnose sys sdwan service | grep -i member
```

- **Purpose:** SD-WAN service steering.
- **Options and filters:** service: health and member selection
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Sessions by source address

```text
diagnose sys session list | grep 192.0.2.10
```

- **Purpose:** Sessions by source address.
- **Options and filters:** list: active sessions
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## BGP peer summary

```text
get router info bgp summary | grep 192.0.2
```

- **Purpose:** BGP peer summary.
- **Options and filters:** summary: condensed peers
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Physical NIC counters

```text
diagnose hardware deviceinfo nic port1 | grep -i error
```

- **Purpose:** Physical NIC counters.
- **Options and filters:** nic port1: chosen interface
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## ARP entries for a host

```text
get system arp | grep 192.0.2.10
```

- **Purpose:** ARP entries for a host.
- **Options and filters:** ARP: IP-to-MAC neighbors
- **Operational example:** Find relevant information while investigating an issue without reading all output.

