---
tags: [cli, dell, os9, show]
validation: not-lab-verified
---

# Show & status — Dell OS9

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Compatibility:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verify with `show version` and `?`.

## `show version`

```text
show version | grep Version
```

- **Purpose:** Identify OS9 release and hardware.
- **Options:** No flags.
- **Real use:** Confirm OS9 before maintenance.

## `show interfaces`

```text
show interfaces | grep error
```

- **Purpose:** Review port state and counters.
- **Options:** No flags.
- **Real use:** Find down links.

## `show ip route`

```text
show ip route | grep 198.51.100
```

- **Purpose:** Inspect IPv4 routes.
- **Options:** No flags.
- **Real use:** Check destination routes.

## `show vlan`

```text
show vlan | grep 10
```

- **Purpose:** Review VLAN inventory on switching platforms.
- **Options:** No flags; availability varies.
- **Real use:** Find VLAN 10.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
