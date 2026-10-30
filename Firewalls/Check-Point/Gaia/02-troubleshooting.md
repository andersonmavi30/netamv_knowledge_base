---
tags: [cli, check-point, gaia, troubleshooting]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert. Confirm installed R8x release and appliance role.

## `fw ctl conntab | grep 192.0.2.10`

```text
fw ctl conntab | grep 192.0.2.10
```

- **Purpose:** Search Firewall connections for a client.
- **Arguments:** conntab: simplified connection table; grep: host text.
- **Use case:** Investigate missing sessions.

## `fw tab -t connections -s`

```text
fw tab -t connections -s
```

- **Purpose:** Inspect connection-table size and entries.
- **Arguments:** -t: kernel table; -s: statistics.
- **Use case:** Investigate table exhaustion.

## `fw ctl pstat | grep -i memory`

```text
fw ctl pstat | grep -i memory
```

- **Purpose:** Filter firewall kernel statistics for memory.
- **Arguments:** pstat: kernel packet/memory statistics; grep -i: case-insensitive.
- **Use case:** Investigate resource alerts.

## `cphaprob stat`

```text
cphaprob stat
```

- **Purpose:** Inspect ClusterXL state when clustering is enabled.
- **Arguments:** stat: member state.
- **Use case:** Check Active/Standby during failover.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/Content/Topics-CLIG/FWG/fw-tab.htm)
