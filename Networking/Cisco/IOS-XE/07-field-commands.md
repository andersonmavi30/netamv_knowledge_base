---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Cisco IOS XE

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** IOS XE (check release). Verify against your device.

## `show ip ospf interface brief`

```text
show ip ospf interface brief | include GigabitEthernet
```

- **Purpose:** Show OSPF interfaces.
- **Parameters:** brief: concise
- **Filter / lookup:** `show ip ospf interface brief | include GigabitEthernet`

## `show ip route ospf`

```text
show ip route ospf | include 198.51.100
```

- **Purpose:** Show OSPF routes.
- **Parameters:** ospf: routing protocol
- **Filter / lookup:** `show ip route ospf | include 198.51.100`

## `show access-lists 101`

```text
show access-lists 101 | include deny
```

- **Purpose:** Inspect ACL 101.
- **Parameters:** 101: ACL ID
- **Filter / lookup:** `show access-lists 101 | include deny`

## `show interfaces GigabitEthernet1/0/1 counters errors`

```text
show interfaces GigabitEthernet1/0/1 counters errors
```

- **Purpose:** Display hardware error counters of one switch interface without showing every port.
- **Parameters:** GigabitEthernet1/0/1: interface ID; counters errors: error-only counter view.
- **Use case:** Look for increasing FCS/receive error counters during an uplink incident; supported on compatible Catalyst IOS XE switches.
- **Official reference:** https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst9300/software/release/17-15/command_reference/b_1715_9300_cr/interface_and_hardware_commands.html

## `show ip sla statistics 1 | include Latest RTT|return code`

```text
show ip sla statistics 1 | include Latest RTT|return code
```

- **Purpose:** Read the latest response time and return code of IP SLA operation 1.
- **Parameters:** statistics 1: selected SLA operation; | include: keep RTT and return-code lines.
- **Use case:** Check whether an active probe reports latency or a failed test.
- **Reference:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/ipsla/command/sla-cr-book/sla_s1.html

> Examples pending lab validation. Confirm the release and syntax with CLI help.
