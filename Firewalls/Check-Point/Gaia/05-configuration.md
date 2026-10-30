---
tags: [cli, check-point, gaia, configuration]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Gaia Clish. Confirm installed R8x release and appliance role.

## `set hostname CP-LAB`

```text
set hostname CP-LAB
```

- **Purpose:** Set a lab Gaia hostname.
- **Arguments:** set hostname: changes hostname.
- **Use case:** Identify lab gateway.
- **Caution:** Run `save config` separately after validation.

## `set interface eth1 ipv4-address 192.0.2.1 mask-length 24`

```text
set interface eth1 ipv4-address 192.0.2.1 mask-length 24
```

- **Purpose:** Assign an IPv4 interface address.
- **Arguments:** eth1: port; mask-length: CIDR.
- **Use case:** Stage a lab LAN interface.
- **Caution:** Can disconnect management after change.

## `show interface eth1`

```text
show interface eth1
```

- **Purpose:** Verify interface settings before saving.
- **Arguments:** show interface: targeted state.
- **Use case:** Review IP/mask.

## `save config`

```text
save config
```

- **Purpose:** Persist Gaia configuration changes.
- **Arguments:** save config: writes persistent config.
- **Use case:** Keep reviewed lab changes after reboot.
- **Caution:** Gaia configuration is separate from SmartConsole security policy installation.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-commands-for-network-interfaces.htm)
