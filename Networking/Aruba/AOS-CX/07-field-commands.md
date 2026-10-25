---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Field checks

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify model and release.

## `show lacp aggregates | include lag1`

```text
show lacp aggregates | include lag1
```

- **Purpose:** Inspect LACP aggregation.
- **Arguments:** include: lag name.
- **Use case:** Diagnose LAG.

## `show ntp associations | include 192.0.2`

```text
show ntp associations | include 192.0.2
```

- **Purpose:** Find NTP associations.
- **Arguments:** include: IP pattern.
- **Use case:** Check time peers.

## `show interface 1/1/4 | include error`

```text
show interface 1/1/4 | include error
```

- **Purpose:** Inspect port errors.
- **Arguments:** include: error keyword.
- **Use case:** Find physical issues.

## `show ip route | include 203.0.113`

```text
show ip route | include 203.0.113
```

- **Purpose:** Find a routed prefix.
- **Arguments:** include: prefix match.
- **Use case:** Check route.

> Lab validation required. Mirror/tshark need platform support and authorization; disable after use.
