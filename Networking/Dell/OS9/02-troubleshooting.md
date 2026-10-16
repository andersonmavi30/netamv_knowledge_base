---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Troubleshooting — Dell OS9

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Purpose:** Review errors and link state.
- **Parameters:** Output depends on interface type.
- **Practical use:** Investigate packet drops.
- **Verification:** `show interfaces`

## `show logging`

```text
show logging
```

- **Purpose:** Review system events.
- **Parameters:** No arguments.
- **Practical use:** Find port transition events.
- **Verification:** `show logging`

## `show ip route`

```text
show ip route
```

- **Purpose:** Inspect reachability and installed routes.
- **Parameters:** No arguments.
- **Practical use:** Find missing route.
- **Verification:** `show ip route`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
