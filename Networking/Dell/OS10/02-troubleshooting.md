---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Troubleshooting — Dell OS10

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Reference scope:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show interface`

```text
show interface
```

- **Purpose:** Inspect interface health.
- **Parameters:** Add interface ID per model.
- **Practical use:** Find uplink errors.
- **Verification:** `show interface`

## `show logging`

```text
show logging
```

- **Purpose:** Inspect OS10 events where available.
- **Parameters:** CLI variants may vary by release.
- **Practical use:** Investigate link flap.
- **Verification:** `show logging`

## `show ip route`

```text
show ip route
```

- **Purpose:** Review routing table.
- **Parameters:** No arguments.
- **Practical use:** Confirm expected route.
- **Verification:** `show ip route`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
