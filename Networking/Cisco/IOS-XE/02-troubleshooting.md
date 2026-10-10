---
tags: [cli, cisco, ios-xe, troubleshooting]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🛠️ Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS XE · **Compatibility:** Cisco IOS XE 17.x (device/model-specific; verify your release).

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Purpose:** Test ICMP connectivity to an IPv4 destination.
- **Arguments:** IP: target host.
- **Use case:** Confirm reachability from the router.

## `traceroute 192.0.2.10`

```text
traceroute 192.0.2.10
```

- **Purpose:** Display hop-by-hop path toward an IPv4 destination.
- **Arguments:** IP: destination.
- **Use case:** Locate a path failure.

## `show logging`

```text
show logging
```

- **Purpose:** Inspect buffered system messages.
- **Arguments:** No arguments.
- **Use case:** Find link flap events.

## `show interfaces GigabitEthernet1/0/1`

```text
show interfaces GigabitEthernet1/0/1
```

- **Purpose:** Review link state, duplex, counters and errors.
- **Arguments:** Interface name: choose a real port on your device.
- **Use case:** Look for input errors and discards.

> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
