---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify installed release with `show version` and `?`.

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Purpose:** Test reachability to a host.
- **Arguments:** IP: target address.
- **Use case:** Check management server.

## `traceroute 198.51.100.10`

```text
traceroute 198.51.100.10
```

- **Purpose:** Trace hops to a remote host.
- **Arguments:** IP: target.
- **Use case:** Locate routing failure.

## `show logging | include link`

```text
show logging | include link
```

- **Purpose:** Find link-related log messages.
- **Arguments:** include: text filter.
- **Use case:** Investigate flapping.

## `show arp | include 192.0.2.10`

```text
show arp | include 192.0.2.10
```

- **Purpose:** Find an ARP neighbor.
- **Arguments:** include: IP match.
- **Use case:** Confirm gateway MAC.

> Examples pending lab validation; availability varies by release and hardware.
