---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Show & status — Dell OS10

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Reference scope:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show version`

```text
show version
```

- **Purpose:** Identify OS10 version.
- **Parameters:** No arguments.
- **Practical use:** Check release before troubleshooting.
- **Verification:** `show version`

## `show interface status`

```text
show interface status
```

- **Purpose:** Summarize interface states; validate on your build.
- **Parameters:** status: summary.
- **Practical use:** Find down links.
- **Verification:** `show interface status`

## `show ip route`

```text
show ip route
```

- **Purpose:** Display route information.
- **Parameters:** No arguments.
- **Practical use:** Find installed prefixes.
- **Verification:** `show ip route`

## `show vlan`

```text
show vlan
```

- **Purpose:** Inspect VLANs.
- **Parameters:** No arguments.
- **Practical use:** Check VLAN inventory.
- **Verification:** `show vlan`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
