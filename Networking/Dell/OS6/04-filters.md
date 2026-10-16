---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Filters — Dell OS6

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS6 — generally N-series (check model/release).

## `show running-config`

```text
show running-config
```

- **Purpose:** Review configuration; confirm whether pipe filters are supported on this release.
- **Parameters:** Output filters differ across OS6 revisions.
- **Practical use:** Find interface settings.
- **Verification:** `show running-config`

## `show logging`

```text
show logging
```

- **Purpose:** Inspect events before applying platform-specific filters.
- **Parameters:** Check available filters with on-device ?.
- **Practical use:** Investigate port flaps.
- **Verification:** `show logging`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
