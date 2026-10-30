---
tags: [cli, check-point, gaia, interfaces]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Interfaces & routing

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert → clish. Confirm installed R8x release and appliance role.

## `clish -c "show interface eth1"`

```text
clish -c "show interface eth1"
```

- **Purpose:** Inspect one physical interface.
- **Arguments:** eth1: example interface name.
- **Use case:** Check an uplink state.

## `clish -c "show interfaces all" | grep eth1`

```text
clish -c "show interfaces all" | grep eth1
```

- **Purpose:** Filter interface inventory to a target port.
- **Arguments:** all: all interfaces; grep: text match.
- **Use case:** Find a specific port without reviewing all.

## `clish -c "show route all" | grep 198.51.100`

```text
clish -c "show route all" | grep 198.51.100
```

- **Purpose:** Search Gaia routing output by prefix.
- **Arguments:** route all: route view; grep: textual search.
- **Use case:** Investigate a missing remote subnet.

## `fw ctl iflist | grep eth1`

```text
fw ctl iflist | grep eth1
```

- **Purpose:** Inspect kernel-visible interfaces by name.
- **Arguments:** iflist: kernel interfaces; grep: interface name.
- **Use case:** Compare firewall kernel and Gaia interface list.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-commands-for-network-interfaces.htm)
