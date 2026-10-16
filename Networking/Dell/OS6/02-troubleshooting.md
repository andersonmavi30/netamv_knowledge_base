---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Troubleshooting — Dell OS6

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS6 — generally N-series (check model/release).

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Purpose:** Test IPv4 connectivity.
- **Parameters:** IP: destination.
- **Practical use:** Test management reachability.
- **Verification:** `ping 192.0.2.10`

## `show interfaces counters`

```text
show interfaces counters
```

- **Purpose:** Inspect traffic counters where supported.
- **Parameters:** counters: interface statistics.
- **Practical use:** Find drops or errors.
- **Verification:** `show interfaces counters`

## `show logging`

```text
show logging
```

- **Purpose:** Review recent errors and events.
- **Parameters:** No arguments.
- **Practical use:** Identify link-down time.
- **Verification:** `show logging`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
