---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Filters — Dell OS9

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Purpose:** Inspect output before selecting OS9-specific CLI filters.
- **Parameters:** Pipe options differ across releases; verify with ?.
- **Practical use:** Search operational data.
- **Verification:** `show interfaces`

## `show ip route`

```text
show ip route
```

- **Purpose:** Review route output before platform-specific filtering.
- **Parameters:** Use CLI help for exact filter syntax.
- **Practical use:** Find destination networks.
- **Verification:** `show ip route`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
