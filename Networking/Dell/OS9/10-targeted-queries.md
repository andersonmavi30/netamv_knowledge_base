---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Dell OS9

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Configured hostname

```text
show running-config | grep hostname
```

- **Purpose:** Configured hostname.
- **Options and filters:** grep: matching lines
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Interface CRC errors

```text
show interfaces | grep CRC
```

- **Purpose:** Interface CRC errors.
- **Options and filters:** grep: select lines
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Link state alarms

```text
show logging | grep DOWN
```

- **Purpose:** Link state alarms.
- **Options and filters:** grep: event search
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Route prefix search

```text
show ip route | grep 203.0.113
```

- **Purpose:** Route prefix search.
- **Options and filters:** grep: text filter
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## SNMP configuration

```text
show running-config | grep snmp
```

- **Purpose:** SNMP configuration.
- **Options and filters:** grep: matching lines
- **Operational example:** Find relevant information while investigating an issue without reading all output.

