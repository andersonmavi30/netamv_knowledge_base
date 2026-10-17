---
tags: [cli, cisco-ios-xe, operations]
validation: not-lab-verified
---

# 📋 Additional operational commands

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Index](README.md)

**Version family:** 17.x. Availability varies with model, license and release.

## `show ip ospf neighbor`

```text
show ip ospf neighbor
```

- **Purpose:** Inspect OSPF adjacencies.
- **Parameters:** No arguments.
- **Operational example:** Check FULL neighbors.
- **Filter/verification:** `show ip ospf neighbor | include FULL`

## `show ip bgp summary`

```text
show ip bgp summary
```

- **Purpose:** Inspect BGP peer states when supported.
- **Parameters:** summary: condensed output.
- **Operational example:** Find Idle peers.
- **Filter/verification:** `show ip bgp summary | include Idle|Active`

## `show access-lists`

```text
show access-lists
```

- **Purpose:** Display ACL entries and matches.
- **Parameters:** No arguments.
- **Operational example:** Find ACL 101.
- **Filter/verification:** `show access-lists 101`

## `show ip arp`

```text
show ip arp
```

- **Purpose:** Display ARP neighbors.
- **Parameters:** No arguments.
- **Operational example:** Check gateway MAC.
- **Filter/verification:** `show ip arp | include 192.0.2.10`

## `show interfaces status`

```text
show interfaces status
```

- **Purpose:** Show port summary on switching platforms.
- **Parameters:** Platform dependent.
- **Operational example:** Locate down or err-disabled ports.
- **Filter/verification:** `show interfaces status | include notconnect|err-disabled`


## `show ip route 198.51.100.10`

```text
show ip route 198.51.100.10
```

- **Purpose:** Lookup the best route for the destination.
- **Parameters:** destination IP: targeted lookup.
- **Operational example:** Verify traffic uses expected next-hop.
- **Filter/verification:** `show ip route 198.51.100.10`

## `show running-config | section ^router`

```text
show running-config | section ^router
```

- **Purpose:** Review router configuration blocks.
- **Parameters:** section: matching config blocks.
- **Operational example:** Find OSPF or BGP configuration.
- **Filter/verification:** `show running-config | section ^router`

> Not lab-tested; verify against release-specific CLI help. Full backups and debug output may expose sensitive information.
