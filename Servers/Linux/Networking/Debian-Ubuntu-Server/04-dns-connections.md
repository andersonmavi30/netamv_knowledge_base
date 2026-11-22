---
tags: [linux, networking, cli, servers, debian]
validation: not-lab-verified
---

# DNS and network connections

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ Debian / Ubuntu Server](README.md)

**Platform:** Debian / Ubuntu Server. Ubuntu Server may use Netplan with `systemd-networkd`; Debian can use ifupdown, NetworkManager, or systemd-networkd. `resolvectl` only works with active `systemd-resolved`; `nmcli` is not universal.

## `resolvectl status`

```bash
resolvectl status
```

- **Purpose:** Inspect DNS servers, domains and resolver settings for systemd-resolved and its links.
- **Arguments:** `status`: display resolver and per-link DNS state; requires systemd-resolved/resolvectl availability.
- **Use case:** Investigate unexpected DNS resolution on an Ubuntu host.
- **Official reference:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Not lab-verified.

## `resolvectl query example.com`

```bash
resolvectl query example.com
```

- **Purpose:** Resolve a domain through systemd-resolved and display the result.
- **Arguments:** `query`: DNS/name lookup; `example.com`: sample domain; requires active systemd-resolved.
- **Use case:** Test whether Ubuntu Server can resolve DNS names via its configured resolver.
- **Official reference:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Not lab-verified.
