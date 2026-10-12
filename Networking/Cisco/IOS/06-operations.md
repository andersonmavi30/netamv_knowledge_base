---
tags: [cli, cisco-ios-classic, operations]
validation: not-lab-verified
---

# 📋 Additional operational commands

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Index](README.md)

**Version family:** 15.x. Availability varies with model, license and release.

## `show ip ospf neighbor`

```text
show ip ospf neighbor
```

- **Purpose:** Show OSPF adjacencies.
- **Parameters:** No arguments.
- **Operational example:** Find neighbors in FULL state.
- **Filter/verification:** `show ip ospf neighbor | include FULL`

## `show ip protocols`

```text
show ip protocols
```

- **Purpose:** Inspect active routing protocols.
- **Parameters:** No arguments.
- **Operational example:** Check configured routing networks.
- **Filter/verification:** `show ip protocols | include Routing Protocol`

## `show access-lists`

```text
show access-lists
```

- **Purpose:** Show configured ACLs and counters.
- **Parameters:** No arguments.
- **Operational example:** Find ACL 101 rules.
- **Filter/verification:** `show access-lists 101`

## `show cdp neighbors detail`

```text
show cdp neighbors detail
```

- **Purpose:** Display connected Cisco neighbor details.
- **Parameters:** detail: includes device and IP data.
- **Operational example:** Find the peer on a lab link.
- **Filter/verification:** `show cdp neighbors detail | include Device ID|IP address`

## `show ip arp`

```text
show ip arp
```

- **Purpose:** Show IPv4-to-MAC neighbor mappings.
- **Parameters:** No arguments.
- **Operational example:** Find a host MAC.
- **Filter/verification:** `show ip arp | include 192.0.2.10`

## `show interfaces status`

```text
show interfaces status
```

- **Purpose:** List switchport status (on supporting switches).
- **Parameters:** status: port summary; platform-dependent.
- **Operational example:** Find err-disabled/down ports.
- **Filter/verification:** `show interfaces status | include notconnect|err-disabled`

## `show spanning-tree`

```text
show spanning-tree
```

- **Purpose:** Inspect STP topology on L2-capable platforms.
- **Parameters:** No arguments; switch feature required.
- **Operational example:** Find blocked interfaces.
- **Filter/verification:** `show spanning-tree | include BLK`

## `show vlan brief`

```text
show vlan brief
```

- **Purpose:** List VLANs on switches that support this command.
- **Parameters:** brief: summary.
- **Operational example:** Find VLAN 10.
- **Filter/verification:** `show vlan brief | include 10`

> Not lab-tested; verify against release-specific CLI help. Full backups and debug output may expose sensitive information.
