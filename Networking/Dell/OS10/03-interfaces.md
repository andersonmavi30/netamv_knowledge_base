---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Interfaces — Dell OS10

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Reference scope:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show interface status`

```text
show interface status
```

- **Purpose:** Review interface status.
- **Parameters:** status: summary.
- **Practical use:** Find a link that is down.
- **Verification:** `show interface status`

## `show running-configuration`

```text
show running-configuration
```

- **Purpose:** Inspect current configuration.
- **Parameters:** No arguments.
- **Practical use:** Check port descriptions.
- **Verification:** `show running-configuration`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
