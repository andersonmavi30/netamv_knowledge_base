---
tags: [linux, networking, cli, servers, rhel]
validation: not-lab-verified
---

# DNS and network connections

[🇬🇧 English](04-dns-connections.md) · [🇨🇴 Español](04-dns-connections.es.md) · [↩ RHEL / Rocky Linux / AlmaLinux / Fedora](README.md)

**Platform:** RHEL / Rocky Linux / AlmaLinux / Fedora. NetworkManager is commonly used on these distributions; `nmcli` requires the service to be active. `resolvectl` depends on `systemd-resolved` and is not assumed to be installed.

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

## `nmcli -f GENERAL,IP4 device show eth0`

```bash
nmcli -f GENERAL,IP4 device show eth0
```

- **Purpose:** Display general properties and IPv4 configuration for a NetworkManager device.
- **Arguments:** `-f GENERAL,IP4`: select fields; `device show`: inspect properties; `eth0`: example interface. Requires NetworkManager.
- **Use case:** Check an active RHEL interface's IPv4 address and gateway.
- **Official reference:** https://networkmanager.dev/docs/api/latest/nmcli.html

> Not lab-verified.
