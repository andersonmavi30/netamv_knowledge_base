---
tags: [cli, dell, os10, configuration]
validation: not-lab-verified
---

# Configuration — Dell OS10

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Compatibility:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verify with `show version` and `?`.

## `hostname DELL-LAB`

```text
configure terminal
hostname DELL-LAB
end
```

- **Purpose:** Configure device hostname.
- **Options:** hostname: device name.
- **Real use:** Name lab switch.

## `copy running-configuration startup-configuration`

```text
copy running-configuration startup-configuration
```

- **Purpose:** Save checked configuration.
- **Options:** running-configuration: source; startup-configuration: target.
- **Real use:** Persist config.

## `show startup-configuration`

```text
show startup-configuration
```

- **Purpose:** Check saved settings.
- **Options:** No flags.
- **Real use:** Compare with running configuration.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
