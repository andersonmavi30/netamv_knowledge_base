---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Packet diagnostics — Dell OS10

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference scope:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show interface`

```text
show interface
```

- **Purpose:** Inspect port error counters before attempting capture.
- **Parameters:** Interface-specific forms vary by model.
- **Practical use:** Determine whether traffic drops.
- **Verification:** `show interface`

## `show logging`

```text
show logging
```

- **Purpose:** Inspect control-plane events; not a raw-packet capture.
- **Parameters:** Confirm logging CLI against OS10 release.
- **Practical use:** Locate timing of link failure.
- **Verification:** `show logging`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
