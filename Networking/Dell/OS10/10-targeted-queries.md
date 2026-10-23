---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Targeted operational queries — Dell OS10

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Illustrative examples: verify platform, release and CLI help before use.

## Interfaces with link down

```text
show interface status | grep down
```

- **Purpose:** Interfaces with link down.
- **Options and filters:** grep: matching lines
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Route prefix search

```text
show ip route | grep 203.0.113
```

- **Purpose:** Route prefix search.
- **Options and filters:** grep: text filter
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## SNMP settings

```text
show running-configuration | grep snmp
```

- **Purpose:** SNMP settings.
- **Options and filters:** grep: matching lines
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## Specific port errors

```text
show interface ethernet 1/1/5 | grep error
```

- **Purpose:** Specific port errors.
- **Options and filters:** grep: case-sensitive text
- **Operational example:** Find relevant information while investigating an issue without reading all output.

## VLAN 20 presence

```text
show vlan | grep 20
```

- **Purpose:** VLAN 20 presence.
- **Options and filters:** grep: text match
- **Operational example:** Find relevant information while investigating an issue without reading all output.

