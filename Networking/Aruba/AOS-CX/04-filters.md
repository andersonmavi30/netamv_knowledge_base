---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Output filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify installed release with `show version` and `?`.

## `show running-config | include hostname`

```text
show running-config | include hostname
```

- **Purpose:** Match hostname line.
- **Arguments:** include: keep matching lines.
- **Use case:** Identify switch.

## `show running-config | exclude description`

```text
show running-config | exclude description
```

- **Purpose:** Hide description lines.
- **Arguments:** exclude: remove matches.
- **Use case:** Review operational configuration.

## `show running-config | begin vlan`

```text
show running-config | begin vlan
```

- **Purpose:** Start output at VLAN configuration.
- **Arguments:** begin: start at first match.
- **Use case:** Inspect VLAN blocks.

## `show interface brief | include down | count`

```text
show interface brief | include down | count
```

- **Purpose:** Count down-matching output lines.
- **Arguments:** count: number of filtered lines.
- **Use case:** Estimate down ports.

> Examples pending lab validation; availability varies by release and hardware.
