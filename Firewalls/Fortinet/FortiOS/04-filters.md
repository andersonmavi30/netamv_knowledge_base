---
tags: [cli, fortinet, fortios, filters]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔍 Output filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Fortinet](../README.md)

**Platform:** Fortinet / FortiOS · **Compatibility:** FortiOS 7.x (verify your exact release).

## `get system status | grep Version`

```text
get system status | grep Version
```

- **Purpose:** Show lines containing Version.
- **Arguments:** |: pipe; grep: text match.
- **Use case:** Find firmware version quickly.

## `get system status | grep -i hostname`

```text
get system status | grep -i hostname
```

- **Purpose:** Search output ignoring case.
- **Arguments:** -i: case-insensitive.
- **Use case:** Find hostname even if capitalization differs.

## `show system interface | grep -f port3`

```text
show system interface | grep -f port3
```

- **Purpose:** Show the matching configuration block with context (where supported).
- **Arguments:** -f: configuration-context output.
- **Use case:** Locate the port3 settings.

## `get system interface | grep -n port3`

```text
get system interface | grep -n port3
```

- **Purpose:** Show matching lines with line numbers.
- **Arguments:** -n: line numbers.
- **Use case:** Find port3 in long output.

> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
