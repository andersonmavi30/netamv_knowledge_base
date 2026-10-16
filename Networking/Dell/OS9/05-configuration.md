---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Configuration — Dell OS9

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `configure`

```text
configure
hostname DELL-LAB
end
```

- **Purpose:** Set hostname in a lab configuration.
- **Parameters:** configure: config mode; hostname: system name; end: leave.
- **Practical use:** Rename switch.
- **Verification:** `show running-config`

## `write memory`

```text
write memory
```

- **Purpose:** Save configuration on supported OS9 trains.
- **Parameters:** write memory: persist settings.
- **Practical use:** Keep approved settings after reload.
- **Verification:** `show running-config`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
