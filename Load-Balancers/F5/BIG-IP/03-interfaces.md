---
tags: [cli, f5, big-ip, tmos, interfaces]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Networking & routes

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh show net interface 1.1`

```text
tmsh show net interface 1.1
```

- **Purpose:** Inspect physical interface 1.1.
- **Arguments:** 1.1: example port on supported hardware.
- **Use case:** Diagnose link drops.

## `tmsh list net self | grep 192.0.2`

```text
tmsh list net self | grep 192.0.2
```

- **Purpose:** Find Self IP configuration by subnet.
- **Arguments:** net self: BIG-IP local addresses; grep: subnet text.
- **Use case:** Confirm the server VLAN's Self IP.

## `tmsh list net vlan | grep -i external`

```text
tmsh list net vlan | grep -i external
```

- **Purpose:** Identify the external VLAN.
- **Arguments:** grep -i: case-insensitive name filter.
- **Use case:** Map outside interface to VLAN.

## `tmsh show net route lookup 198.51.100.10`

```text
tmsh show net route lookup 198.51.100.10
```

- **Purpose:** Perform a route lookup to a destination.
- **Arguments:** lookup: forwarding lookup for one address.
- **Use case:** Check reachability to backend networks.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v14/modules/net/net_route.html)
