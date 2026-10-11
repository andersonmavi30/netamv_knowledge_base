---
tags: [cli, cisco, ios-xe, interfaces]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🔌 Interface configuration

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS XE · **Compatibility:** Cisco IOS XE 17.x (device/model-specific; verify your release).

## `show running-config interface GigabitEthernet1/0/1`

```text
show running-config interface GigabitEthernet1/0/1
```

- **Purpose:** Review a port's current running configuration.
- **Arguments:** Interface ID varies by platform.
- **Use case:** Compare before making a change.

- **Practical filter:** `show running-config | section ^interface GigabitEthernet1/0/1` — Filter or verify relevant data; inspect full output when more context is needed.

## `configure terminal`

```text
configure terminal
interface GigabitEthernet1/0/1
 description LAB-UPLINK
 no shutdown
end
```

- **Purpose:** Set an interface description and administratively enable it.
- **Arguments:** configure terminal: configuration mode; interface: select port; description: label; no shutdown: enable; end: exit.
- **Use case:** Activate a lab-facing link.
- **Caution:** Enabling a port changes live connectivity. Confirm the port role first.

- **Practical filter:** `show ip interface brief | include GigabitEthernet1/0/1` — Filter or verify relevant data; inspect full output when more context is needed.

## `show ip interface brief`

```text
show ip interface brief
```

- **Purpose:** Validate address and line status after configuration.
- **Arguments:** brief: summary.
- **Use case:** Confirm interface is up/up when the link is active.

- **Practical filter:** `show ip interface brief | include GigabitEthernet1/0/1` — Filter or verify relevant data; inspect full output when more context is needed.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Purpose:** Save current running configuration for reload persistence.
- **Arguments:** running-config: source; startup-config: destination.
- **Use case:** Save only after validating desired changes.
- **Caution:** Saving overwrites the saved startup configuration.

- **Practical filter:** `show running-config | section ^interface GigabitEthernet1/0/1` — Filter or verify relevant data; inspect full output when more context is needed.


> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
