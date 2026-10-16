---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Packet diagnostics — Dell OS6

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS6 — generally N-series (check model/release).

## `show interfaces counters`

```text
show interfaces counters
```

- **Purpose:** Use interface counters as an initial packet-loss diagnostic.
- **Parameters:** counters: error/traffic statistics.
- **Practical use:** Look for increasing discard counters.
- **Verification:** `show interfaces counters`

## `show logging`

```text
show logging
```

- **Purpose:** Review link and protocol events.
- **Parameters:** No flags; filtering is release-dependent.
- **Practical use:** Investigate frequent link flaps.
- **Verification:** `show logging`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
