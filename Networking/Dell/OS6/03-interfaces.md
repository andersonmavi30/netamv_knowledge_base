---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Interfaces — Dell OS6

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS6 — generally N-series (check model/release).

## `show interfaces status`

```text
show interfaces status
```

- **Purpose:** Review port status before changes.
- **Parameters:** status: short view.
- **Practical use:** Find uplink state.
- **Verification:** `show interfaces status`

## `configure`

```text
configure
interface gigabitethernet 1/0/1
 description LAB-UPLINK
exit
exit
```

- **Purpose:** Label a test port; exact interface syntax varies by model.
- **Parameters:** interface: select port; description: label.
- **Practical use:** Mark a lab uplink.
- **Verification:** `show interfaces status`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
