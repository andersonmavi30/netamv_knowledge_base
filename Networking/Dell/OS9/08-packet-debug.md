---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Packet diagnostics — Dell OS9

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Purpose:** Use interface counters to narrow traffic faults.
- **Parameters:** Check counters on target port.
- **Practical use:** Check errors and drops.
- **Verification:** `show interfaces`

## `show logging`

```text
show logging
```

- **Purpose:** Inspect control-plane events; not a PCAP capture.
- **Parameters:** No flags.
- **Practical use:** Trace link flap timeline.
- **Verification:** `show logging`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
