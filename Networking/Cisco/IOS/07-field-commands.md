---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Operational commands — Cisco IOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Reference version:** IOS classic (check release). Verify against your device.

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
- **Parameters:** ospf: route source
- **Filter / lookup:** `show ip route ospf | include 198.51.100`

## `show access-lists 101`

```text
show access-lists 101 | include deny
```

- **Purpose:** Inspect ACL 101.
- **Parameters:** 101: ACL ID
- **Filter / lookup:** `show access-lists 101 | include deny`

## `show ip route connected | include 192.0.2`

```text
show ip route connected | include 192.0.2
```

- **Purpose:** Filter the routing table to connected routes containing the 192.0.2 prefix.
- **Parameters:** connected: routes learned from directly attached interfaces; | include: matching prefix lines.
- **Use case:** Verify whether the lab LAN subnet is installed as directly connected.
- **Official reference:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html

## `show ip interface GigabitEthernet0/0 | include access list`

```text
show ip interface GigabitEthernet0/0 | include access list
```

- **Purpose:** Show inbound and outbound IP ACL assignments on one routed interface.
- **Parameters:** GigabitEthernet0/0: target interface; | include access list: filter ACL lines.
- **Use case:** Verify whether an interface ACL might be blocking a test host.
- **Reference:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/ipaddr_acl/configuration/xe-17/sec-ip-addr-acl-xe-17-book.html

> Examples pending lab validation. Confirm the release and syntax with CLI help.
