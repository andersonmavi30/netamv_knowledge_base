---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Cisco IOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** IOS classic (check release). Verify against your device.

## `show ip ospf interface brief`

```text
show ip ospf interface brief
```

- **Purpose:** Show OSPF interfaces.
- **Parameters:** brief: concise
- **Filter / lookup:** `show ip ospf interface brief | include GigabitEthernet`

## `show ip route ospf`

```text
show ip route ospf
```

- **Purpose:** Show OSPF routes.
- **Parameters:** ospf: route source
- **Filter / lookup:** `show ip route ospf | include 198.51.100`

## `show access-lists 101`

```text
show access-lists 101
```

- **Purpose:** Inspect ACL 101.
- **Parameters:** 101: ACL ID
- **Filter / lookup:** `show access-lists 101 | include deny`



> Examples pending lab validation. Confirm the release and syntax with CLI help.
