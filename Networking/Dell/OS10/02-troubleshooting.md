---
tags: [cli, dell, os10, troubleshooting]
validation: not-lab-verified
---

# Troubleshooting — Dell OS10

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Compatibility:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verify with `show version` and `?`.

## `show logging`

```text
show logging | grep DOWN
```

- **Purpose:** Inspect log events.
- **Options:** No flags.
- **Real use:** Investigate link flaps.

## `show interface ethernet 1/1/1`

```text
show interface ethernet 1/1/1
```

- **Purpose:** Inspect a physical interface.
- **Options:** 1/1/1: node/slot/port.
- **Real use:** Look for link drops.

## `show mac address-table`

```text
show mac address-table
```

- **Purpose:** Review L2 forwarding table on compatible releases.
- **Options:** No flags.
- **Real use:** Locate learned MAC.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
