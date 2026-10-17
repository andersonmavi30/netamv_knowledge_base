---
tags: [cli, dell, os9, filters]
validation: not-lab-verified
---

# Output filters — Dell OS9

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Compatibility:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verify with `show version` and `?`.

## `show running-config | grep hostname`

```text
show running-config | grep hostname
```

- **Purpose:** Filter hostname from full configuration.
- **Options:** | grep: matching lines.
- **Real use:** Identify switch name.

## `show interfaces | grep error`

```text
show interfaces | grep error
```

- **Purpose:** Show lines mentioning port errors.
- **Options:** | grep: case-sensitive match.
- **Real use:** Spot port faults.

## `show ip route | grep 198.51.100`

```text
show ip route | grep 198.51.100
```

- **Purpose:** Find a route prefix by text.
- **Options:** | grep: text, not route lookup.
- **Real use:** Locate a lab prefix.

## `show logging | except INFO`

```text
show logging | except INFO
```

- **Purpose:** Hide lines labeled INFO.
- **Options:** | except: exclude matches.
- **Real use:** Focus on critical events.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
