---
tags: [cli, check-point, gaia, operations]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Firewall operations

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert. Confirm installed R8x release and appliance role.

## `fwaccel stat`

```text
fwaccel stat
```

- **Purpose:** Check SecureXL acceleration status.
- **Arguments:** stat: acceleration statistics/status.
- **Use case:** Investigate low throughput.

## `fw ctl multik stat`

```text
fw ctl multik stat
```

- **Purpose:** Inspect CoreXL firewall instances.
- **Arguments:** multik stat: worker statistics.
- **Use case:** Identify distribution across workers.

## `cpstat fw -f all | grep -i policy`

```text
cpstat fw -f all | grep -i policy
```

- **Purpose:** Search firewall status for policy data.
- **Arguments:** -f all: extended output; grep: policy label.
- **Use case:** Check current installed policy information.

## `cphaprob -a if`

```text
cphaprob -a if
```

- **Purpose:** Inspect ClusterXL interface health.
- **Arguments:** -a if: interface monitoring.
- **Use case:** Diagnose sync interface errors.
- **Caution:** ClusterXL only.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/Content/Topics-CLIG/FWG/fw-ctl.htm)
