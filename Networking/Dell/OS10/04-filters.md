---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Filters — Dell OS10

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Reference scope:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show running-configuration`

```text
show running-configuration
```

- **Purpose:** Inspect the configuration before trying version-specific filters.
- **Parameters:** Verify pipe and regex support with CLI help.
- **Practical use:** Find exact interface block.
- **Verification:** `show running-configuration`

## `show ip route`

```text
show ip route
```

- **Purpose:** Review routes; use supported filter syntax after validation.
- **Parameters:** OS10 syntax is not identical to Cisco IOS.
- **Practical use:** Trace destination route.
- **Verification:** `show ip route`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
