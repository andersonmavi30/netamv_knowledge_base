---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Configuration — Dell OS6

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS6 — generally N-series (check model/release).

## `configure`

```text
configure
hostname DELL-LAB
exit
```

- **Purpose:** Set the device hostname on supported OS6 versions.
- **Parameters:** hostname: device name.
- **Practical use:** Identify lab switch.
- **Verification:** `show running-config`

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Purpose:** Save active configuration where supported.
- **Parameters:** running-config: source; startup-config: destination.
- **Practical use:** Keep tested changes after reboot.
- **Verification:** `show running-config`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
