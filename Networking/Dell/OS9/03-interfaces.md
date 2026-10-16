---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Interfaces — Dell OS9

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Purpose:** Check link status and counters.
- **Parameters:** No arguments.
- **Practical use:** Diagnose failing uplink.
- **Verification:** `show interfaces`

## `show running-config`

```text
show running-config
```

- **Purpose:** Review interface blocks before making changes.
- **Parameters:** No arguments.
- **Practical use:** Find active port config.
- **Verification:** `show running-config`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
