---
tags: [cli, dell, os6, interfaces]
validation: not-lab-verified
---

# Interfaces — Dell OS6

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verify with `show version` and `?`.

## `show interfaces switchport`

```text
show interfaces switchport
```

- **Purpose:** Inspect Layer 2 port modes.
- **Options:** No flags.
- **Real use:** Review trunk/access state.

## `show running-config interface gigabitethernet 1/0/1`

```text
show running-config interface gigabitethernet 1/0/1
```

- **Purpose:** Review the configuration of one port.
- **Options:** interface: port selection.
- **Real use:** Check access VLAN before change.

## `interface gigabitethernet 1/0/2`

```text
configure
interface gigabitethernet 1/0/2
 description LAB-UPLINK
 exit
exit
```

- **Purpose:** Set a lab port description.
- **Options:** interface: port; description: label.
- **Real use:** Identify a lab uplink.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
