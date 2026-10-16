---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Show & status — Dell OS9

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Reference scope:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show version`

```text
show version
```

- **Purpose:** Display OS9 release and system information.
- **Parameters:** No arguments.
- **Practical use:** Identify a Force10-derived platform.
- **Verification:** `show version`

## `show interfaces`

```text
show interfaces
```

- **Purpose:** Display operational interface details.
- **Parameters:** No arguments.
- **Practical use:** Review traffic counters.
- **Verification:** `show interfaces`

## `show ip route`

```text
show ip route
```

- **Purpose:** Inspect the routing table.
- **Parameters:** No arguments.
- **Practical use:** Check next hops.
- **Verification:** `show ip route`

## `show vlan`

```text
show vlan
```

- **Purpose:** Display VLAN configuration where switching is supported.
- **Parameters:** No arguments.
- **Practical use:** Locate VLAN 10.
- **Verification:** `show vlan`

> Illustrative, not lab-verified. Dell hardware families have different CLI; consult model/release-specific documentation before execution.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
