---
tags: [cli, dell, os9, troubleshooting]
validation: not-lab-verified
---

# Troubleshooting — Dell OS9

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Compatibility:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verify with `show version` and `?`.

## `show logging`

```text
show logging
```

- **Purpose:** Inspect OS9 log messages.
- **Options:** No flags.
- **Real use:** Review link-flap events.

## `show arp`

```text
show arp
```

- **Purpose:** Check learned ARP neighbors on supporting platforms.
- **Options:** No flags.
- **Real use:** Verify gateway neighbor resolution.

## `show ip ospf neighbor`

```text
show ip ospf neighbor
```

- **Purpose:** Inspect OSPF neighbors where enabled.
- **Options:** No flags.
- **Real use:** Find incomplete adjacencies.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
