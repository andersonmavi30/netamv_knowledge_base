---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Show & status — Dell OS6

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS6 — generally N-series (check model/release).

## `show version`

```text
show version
```

- **Purpose:** Show OS release and hardware details.
- **Parameters:** No arguments.
- **Practical use:** Identify software before maintenance.
- **Verification:** `show version`

## `show interfaces status`

```text
show interfaces status
```

- **Purpose:** Summarize port connection state on supported N-series models.
- **Parameters:** status: port summary.
- **Practical use:** Find disconnected ports.
- **Verification:** `show interfaces status`

## `show vlan`

```text
show vlan
```

- **Purpose:** Show configured VLANs.
- **Parameters:** No arguments.
- **Practical use:** Check VLAN 10.
- **Verification:** `show vlan`

## `show logging`

```text
show logging
```

- **Purpose:** Inspect system logging.
- **Parameters:** No arguments.
- **Practical use:** Find link flap alarms.
- **Verification:** `show logging`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
