---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# Interfaces and addresses

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ Debian / Ubuntu Server](README.md)

**Platform:** Debian / Ubuntu Server. Ubuntu Server may use Netplan with `systemd-networkd`; Debian can use ifupdown, NetworkManager, or systemd-networkd. `resolvectl` only works with active `systemd-resolved`; `nmcli` is not universal.

## `ip -br address show`

```bash
ip -br address show
```

- **Purpose:** Display interfaces and IPv4/IPv6 addresses in a compact table.
- **Arguments:** `-br`: brief output; `address`: IP information; `show`: read-only display.
- **Use case:** Check a Debian/Ubuntu Server VM's addresses after boot.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-address.8.html

> Not lab-verified.

## `ip -br link show`

```bash
ip -br link show
```

- **Purpose:** Show network interface names, administrative/link state and link-layer identifiers in concise form.
- **Arguments:** `-br`: brief display; `link`: link-layer status; `show`: read-only.
- **Use case:** Identify a down NIC on a Linux virtualization host.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-link.8.html

> Not lab-verified.

## `ip -s link show`

```bash
ip -s link show
```

- **Purpose:** Display per-interface RX/TX counters, errors and dropped packets.
- **Arguments:** `-s`: statistics; `link`: interfaces; `show`: read-only.
- **Use case:** Find interface drops while diagnosing slow links.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-link.8.html

> Not lab-verified.

## `ip neigh show`

```bash
ip neigh show
```

- **Purpose:** List IPv4/IPv6 neighbor (ARP/ND) cache entries and states.
- **Arguments:** `neigh`: neighbors; `show`: read-only list.
- **Use case:** Check gateway MAC and neighbor state.
- **Official reference:** https://man7.org/linux/man-pages/man8/ip-neighbour.8.html

> Not lab-verified.
