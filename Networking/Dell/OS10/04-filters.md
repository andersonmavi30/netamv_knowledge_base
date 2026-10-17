---
tags: [cli, dell, os10, filters]
validation: not-lab-verified
---

# Output filters — Dell OS10

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Compatibility:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verify with `show version` and `?`.

## `show running-configuration | grep hostname`

```text
show running-configuration | grep hostname
```

- **Purpose:** Find configured hostname.
- **Options:** | grep: matching lines.
- **Real use:** Identify switch.

## `show interface status | grep down`

```text
show interface status | grep down
```

- **Purpose:** Filter down interfaces.
- **Options:** | grep: text pattern.
- **Real use:** Locate link faults.

## `show ip route | grep 198.51.100`

```text
show ip route | grep 198.51.100
```

- **Purpose:** Search routing output.
- **Options:** | grep: text not forwarding lookup.
- **Real use:** Find lab prefix.

## `show running-configuration | except description`

```text
show running-configuration | except description
```

- **Purpose:** Hide description lines.
- **Options:** | except: suppress matches.
- **Real use:** Focus on config.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
