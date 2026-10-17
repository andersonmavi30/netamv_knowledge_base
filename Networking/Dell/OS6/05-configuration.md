---
tags: [cli, dell, os6, configuration]
validation: not-lab-verified
---

# Configuration — Dell OS6

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verify with `show version` and `?`.

## `hostname DELL-LAB`

```text
configure
hostname DELL-LAB
exit
```

- **Purpose:** Change hostname.
- **Options:** hostname: device name.
- **Real use:** Name a lab switch.

## `vlan 10`

```text
configure
vlan 10
exit
exit
```

- **Purpose:** Create VLAN 10 on supported OS6 switches.
- **Options:** vlan 10: VLAN identifier.
- **Real use:** Prepare test LAN.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Purpose:** Save running configuration.
- **Options:** running-config: source; startup-config: destination.
- **Real use:** Persist approved settings.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
