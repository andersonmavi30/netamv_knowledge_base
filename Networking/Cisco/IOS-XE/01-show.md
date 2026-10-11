---
tags: [cli, cisco, ios-xe, show]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🔎 Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS XE · **Compatibility:** Cisco IOS XE 17.x (device/model-specific; verify your release).

## `show version`

```text
show version
```

- **Purpose:** Display IOS XE version, uptime and hardware details.
- **Arguments:** No arguments.
- **Use case:** Identify the software release.

- **Practical filter:** `show version | include IOS|uptime` — Filter or verify relevant data; inspect full output when more context is needed.

## `show ip interface brief`

```text
show ip interface brief
```

- **Purpose:** Summarize IPv4 interface address and status.
- **Arguments:** brief: concise output.
- **Use case:** Spot an administratively down interface.

- **Practical filter:** `show ip interface brief | include GigabitEthernet` — Filter or verify relevant data; inspect full output when more context is needed.

## `show ip route`

```text
show ip route
```

- **Purpose:** Display the IPv4 routing table.
- **Arguments:** No arguments.
- **Use case:** Check installed routes.

- **Practical filter:** `show ip route 198.51.100.10` — Filter or verify relevant data; inspect full output when more context is needed.

## `show interfaces GigabitEthernet1/0/1`

```text
show interfaces GigabitEthernet1/0/1
```

- **Purpose:** Inspect link state, traffic and error counters.
- **Arguments:** Interface name varies by device model.
- **Use case:** Investigate CRC errors or drops.

- **Practical filter:** `show interfaces GigabitEthernet1/0/1 | include line protocol|errors|drops` — Filter or verify relevant data; inspect full output when more context is needed.


> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
