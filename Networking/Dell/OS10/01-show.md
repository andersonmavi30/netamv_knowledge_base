---
tags: [cli, dell, os10, show]
validation: not-lab-verified
---

# Show & status — Dell OS10

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Compatibility:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verify with `show version` and `?`.

## `show version`

```text
show version
```

- **Purpose:** Identify OS10 version.
- **Options:** No flags.
- **Real use:** Check release.

## `show interface status`

```text
show interface status
```

- **Purpose:** Summarize Ethernet ports.
- **Options:** status: condensed.
- **Real use:** Find down ports.

## `show ip route`

```text
show ip route
```

- **Purpose:** Display routing table.
- **Options:** No flags.
- **Real use:** Find prefix.

## `show vlan`

```text
show vlan
```

- **Purpose:** Display VLAN inventory.
- **Options:** No flags.
- **Real use:** Check VLAN 10.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
