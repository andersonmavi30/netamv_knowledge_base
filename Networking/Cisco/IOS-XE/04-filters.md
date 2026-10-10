---
tags: [cli, cisco, ios-xe, filters]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🔍 Output filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS XE · **Compatibility:** Cisco IOS XE 17.x (device/model-specific; verify your release).

## `show ip interface brief | include GigabitEthernet`

```text
show ip interface brief | include GigabitEthernet
```

- **Purpose:** Keep only matching interface lines.
- **Arguments:** |: pipe; include: matching lines.
- **Use case:** Find GigabitEthernet status quickly.

## `show logging | exclude LINK`

```text
show logging | exclude LINK
```

- **Purpose:** Hide log lines matching LINK.
- **Arguments:** exclude: remove matching lines.
- **Use case:** Focus on other logs.

## `show running-config | section interface`

```text
show running-config | section interface
```

- **Purpose:** Show interface configuration sections.
- **Arguments:** section: include matching configuration blocks.
- **Use case:** Review several interface configs.

## `show running-config | begin interface`

```text
show running-config | begin interface
```

- **Purpose:** Show output from the first matching interface onward.
- **Arguments:** begin: start at first match (not an exact-section filter).
- **Use case:** Jump past the header of the running config.

> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
