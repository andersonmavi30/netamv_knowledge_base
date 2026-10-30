---
tags: [cli, check-point, gaia, show]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert → clish. Confirm installed R8x release and appliance role.

## `clish -c "show version all" | grep -i "Product version"`

```text
clish -c "show version all" | grep -i "Product version"
```

- **Purpose:** Identify installed Gaia release.
- **Arguments:** -c: run a Clish command; grep -i: ignore case.
- **Use case:** Verify OS before maintenance.

## `clish -c "show hostname"`

```text
clish -c "show hostname"
```

- **Purpose:** Show the current device hostname.
- **Arguments:** -c: execute Clish command.
- **Use case:** Identify the gateway reached over SSH.

## `clish -c "show uptime"`

```text
clish -c "show uptime"
```

- **Purpose:** Check gateway uptime.
- **Arguments:** -c: retrieve Gaia Clish output.
- **Use case:** Investigate recent reboot.

## `clish -c "show version os kernel"`

```text
clish -c "show version os kernel"
```

- **Purpose:** Check kernel version.
- **Arguments:** os kernel: targeted kernel release lookup.
- **Use case:** Compare nodes during patch audit.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)
