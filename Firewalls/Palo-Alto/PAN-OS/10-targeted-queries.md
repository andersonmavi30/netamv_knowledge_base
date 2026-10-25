---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Focused operational commands

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

**Compatibility:** PAN-OS generic; check release-specific `?` syntax.

## `show session info`

```text
show session info
```

- **Purpose:** Check session allocation/capacity before investigating resource exhaustion.
- **Arguments:** info: aggregated session statistics; output fields depend on release.
- **Use case:** Check whether session pressure explains connection failures.

## `show admins`

```text
show admins
```

- **Purpose:** Identify current administrative sessions before changes.
- **Arguments:** admins: list of logged-in administrators; intentionally scoped query.
- **Use case:** Avoid concurrent configuration changes.

## `show jobs pending`

```text
show jobs pending
```

- **Purpose:** Find outstanding management tasks without examining history.
- **Arguments:** pending: only pending jobs.
- **Use case:** Check whether a commit is still queued.

## `show system software status`

```text
show system software status
```

- **Purpose:** Inspect process status when management or dataplane services appear unhealthy.
- **Arguments:** status: per-process operational state; verify support with ?.
- **Use case:** Spot a service repeatedly restarting.

## `show system logdb-quota`

```text
show system logdb-quota
```

- **Purpose:** Review log database allocation by category.
- **Arguments:** logdb-quota: log allocation summary.
- **Use case:** Investigate missing traffic logs due to quota.

## `show running resource-monitor`

```text
show running resource-monitor
```

- **Purpose:** Inspect current resource utilization on supported firewalls.
- **Arguments:** resource-monitor: platform resource measurements.
- **Use case:** Correlate throughput issues with resource peaks.

## `show session all filter rule LAB-ALLOW-HTTPS`

```text
show session all filter rule LAB-ALLOW-HTTPS
```

- **Purpose:** Find sessions that matched a named security rule.
- **Arguments:** filter rule: session-table rule-name filter.
- **Use case:** Determine whether a newly committed rule handles traffic.

## `show user group list`

```text
show user group list
```

- **Purpose:** List groups currently known to the firewall.
- **Arguments:** group list: User-ID groups; depends on User-ID integration.
- **Use case:** Confirm a directory group is learned before checking policy.

## `show high-availability flap-statistics`

```text
show high-availability flap-statistics
```

- **Purpose:** Review HA state transitions when investigating unstable failover.
- **Arguments:** flap-statistics: historical HA transitions; HA must be configured.
- **Use case:** Investigate repeated active/passive changes.

## `show dos-block-table`

```text
show dos-block-table
```

- **Purpose:** Inspect blocked sources after a suspected flood.
- **Arguments:** dos-block-table: blocked sources; feature and release dependent.
- **Use case:** Determine whether protection blocked a legitimate client.

> Note: prefer native command filters over pipes when available. Some commands do not support `| match`; check `?`. Not lab verified.

[Official PAN-OS CLI reference](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy)
