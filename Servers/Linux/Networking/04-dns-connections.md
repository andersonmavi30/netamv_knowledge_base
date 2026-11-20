---
tags: [linux, networking, cli, servers]
validation: not-lab-verified
---

# DNS and network connections

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ Index](README.md)

**Platform:** Linux (Rocky/RHEL, Ubuntu, Debian); verify tool availability and version.

## `resolvectl status`

```bash
resolvectl status
```

- **Purpose:** Inspect DNS servers, domains and resolver settings for systemd-resolved and its links.
- **Arguments:** `status`: display resolver and per-link DNS state; requires systemd-resolved/resolvectl availability.
- **Use case:** Investigate unexpected DNS resolution on an Ubuntu host.
- **Official reference:** https://www.freedesktop.org/software/systemd/man/latest/resolvectl.html

> Not lab-verified.

## `nmcli device status`

```bash
nmcli device status
```

- **Purpose:** Show NetworkManager-managed devices and connection state in a concise list.
- **Arguments:** `device`: manage/query network devices; `status`: current device states; requires NetworkManager.
- **Use case:** Check whether a Rocky/RHEL NIC is connected or unmanaged.
- **Official reference:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Not lab-verified.

## `nmcli connection show --active`

```bash
nmcli connection show --active
```

- **Purpose:** List currently active NetworkManager connection profiles and devices.
- **Arguments:** `connection show`: list connections; `--active`: limit to currently activated profiles; read-only.
- **Use case:** Identify the active network profile before troubleshooting a RHEL server.
- **Official reference:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Not lab-verified.
