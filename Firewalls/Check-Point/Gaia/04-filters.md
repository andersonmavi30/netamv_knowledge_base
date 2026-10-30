---
tags: [cli, check-point, gaia, filters]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Output filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert (Bash). Confirm installed R8x release and appliance role.

## `clish -c "show configuration" | grep "static-route"`

```text
clish -c "show configuration" | grep "static-route"
```

- **Purpose:** Find static route configuration lines.
- **Arguments:** -c: Clish command; grep: matching lines.
- **Use case:** Audit static routing settings.

## `clish -c "show version all" | grep -i kernel`

```text
clish -c "show version all" | grep -i kernel
```

- **Purpose:** Focus on kernel build in Gaia version output.
- **Arguments:** grep -i: case-insensitive.
- **Use case:** Check upgrade baseline.

## `tail -n 100 /var/log/messages | grep -i error`

```text
tail -n 100 /var/log/messages | grep -i error
```

- **Purpose:** Search the last 100 syslog lines for errors.
- **Arguments:** -n 100: last 100 lines; grep -i: ignore case.
- **Use case:** Locate recent system alarms.

## `clish -c "show interfaces all" | grep -i "down"`

```text
clish -c "show interfaces all" | grep -i "down"
```

- **Purpose:** Find down-state interface lines.
- **Arguments:** grep -i: case-insensitive text filter.
- **Use case:** Look for an uplink failure.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)
