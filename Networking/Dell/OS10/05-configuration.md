---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Configuration — Dell OS10

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Reference scope:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `configure terminal`

```text
configure terminal
hostname DELL-LAB
end
```

- **Purpose:** Configure device hostname.
- **Parameters:** configure terminal: config mode; hostname: name; end: exit.
- **Practical use:** Name lab switch.
- **Verification:** `show running-configuration`

## `copy running-configuration startup-configuration`

```text
copy running-configuration startup-configuration
```

- **Purpose:** Save OS10 configuration on supporting releases.
- **Parameters:** running-configuration: source; startup-configuration: target.
- **Practical use:** Persist a checked change.
- **Verification:** `show running-configuration`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
