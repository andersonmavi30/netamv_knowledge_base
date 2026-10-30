---
tags: [cli, check-point, gaia, field-commands]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Additional operational checks

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert. Confirm installed R8x release and appliance role.

## `cpstat os -f memory`

```text
cpstat os -f memory
```

- **Purpose:** Check OS memory allocation.
- **Arguments:** -f memory: memory statistics.
- **Use case:** Investigate resource pressure.

## `cpview`

```text
cpview
```

- **Purpose:** Open interactive performance diagnostics.
- **Arguments:** Interactive performance console; quit via its menu.
- **Use case:** Locate high CPU during incident.
- **Caution:** Do not append grep to interactive cpview.

## `vpn tu conn 192.0.2.10 54321 198.51.100.20 443 6`

```text
vpn tu conn 192.0.2.10 54321 198.51.100.20 443 6
```

- **Purpose:** Check a matching encrypted VPN connection.
- **Arguments:** source IP/port, destination IP/port, protocol 6 TCP.
- **Use case:** Investigate missing VPN encryption.

## `clish -c "show ntp"`

```text
clish -c "show ntp"
```

- **Purpose:** View configured NTP settings.
- **Arguments:** -c: execute Gaia Clish read-only.
- **Use case:** Check synchronization configuration.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)
