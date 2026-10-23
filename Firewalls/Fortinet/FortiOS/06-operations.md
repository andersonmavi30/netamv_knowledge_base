---
tags: [cli, fortinet-fortios, operations]
validation: not-lab-verified
---

# 📋 Additional operational commands

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Index](README.md)

**Version family:** 7.x. Availability varies with model, license and release.

## `get firewall policy`

```text
get firewall policy | grep -i name
```

- **Purpose:** List policy summary (available fields vary).
- **Parameters:** No flags.
- **Operational example:** Find active firewall rules.
- **Filter/verification:** `get firewall policy | grep -i name`

## `diagnose sys session stat`

```text
diagnose sys session stat | grep -i session
```

- **Purpose:** Inspect session counts and resource usage.
- **Parameters:** stat: session statistics.
- **Operational example:** Check whether sessions approach limits.
- **Filter/verification:** `diagnose sys session stat | grep -i session`

## `get router info routing-table details 198.51.100.0`

```text
get router info routing-table details 198.51.100.0
```

- **Purpose:** Inspect routes related to a destination; verify supported syntax.
- **Parameters:** details: detailed routing output.
- **Operational example:** Investigate a missing route.
- **Filter/verification:** `get router info routing-table all | grep 198.51.100`

## `diagnose vpn ike gateway list`

```text
diagnose vpn ike gateway list | grep -i name=
```

- **Purpose:** Review IKE gateways and their state.
- **Parameters:** list: gateway output.
- **Operational example:** Review phase-1 status.
- **Filter/verification:** `diagnose vpn ike gateway list | grep -i name=`


## `execute backup full-config tftp lab-backup.conf 192.0.2.20`

```text
execute backup full-config tftp lab-backup.conf 192.0.2.20
```

- **Purpose:** Export encrypted-sensitive full configuration to a trusted TFTP server.
- **Parameters:** filename, server IP: backup destination.
- **Operational example:** Backup before changing a lab firewall.
- **Filter/verification:** `execute backup full-config ?`

## `diagnose debug reset`

```text
diagnose debug reset
```

- **Purpose:** Clear prior debug filter and state.
- **Parameters:** reset: clears debug settings.
- **Operational example:** Prepare a short debug session.
- **Filter/verification:** `diagnose debug status`


> Not lab-tested; verify against release-specific CLI help. Full backups and debug output may expose sensitive information.
