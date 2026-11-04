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

## `fw ctl affinity -l -i eth1`

```text
fw ctl affinity -l -i eth1
```

- **Purpose:** Inspect CoreXL CPU affinity specifically for interface eth1.
- **Arguments:** -l: list current affinities; -i eth1: select interface eth1.
- **Use case:** Check whether an uplink is assigned to the expected CPU during a performance incident.
- **Official reference:** https://sc1.checkpoint.com/documents/R81/WebAdminGuides/EN/CP_R81_PerformanceTuning_AdminGuide/Topics-PTG/CLI/fw-ctl-affinity-l-Gateway-Mode.htm

## `cpstat -f cpu os | grep 'CPU Usage'`

```text
cpstat -f cpu os | grep 'CPU Usage'
```

- **Purpose:** Extract CPU utilization from Gaia statistics in Expert mode.
- **Arguments:** -f cpu: CPU statistics; os: operating system; grep: output filter.
- **Use case:** Validate CPU load before collecting more intrusive diagnostics.
- **Reference:** https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/CP_R82_CLI_ReferenceGuide.pdf

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)

## Installed security policy status

```text
fw stat
```

- **Purpose:** Display the policy installed on a gateway in Expert mode.
- **Parameters / flags:** fw: firewall utility; stat: installed policy information.
- **Operational use:** Confirm that a security policy is loaded after deployment.
- **Reference:** https://sc1.checkpoint.com/

## Cluster status

```text
cphaprob stat
```

- **Purpose:** Show ClusterXL member states from Expert mode.
- **Parameters / flags:** stat: cluster state and member information; requires ClusterXL.
- **Operational use:** Confirm the active/standby state after an HA incident.

## Firewall kernel statistics

```text
fw ctl pstat
```

- **Purpose:** Read firewall kernel performance and allocation statistics in Expert mode.
- **Parameters / flags:** fw ctl: firewall kernel control; pstat: performance statistics.
- **Operational use:** Investigate kernel memory or packet-processing pressure.
- **Validation:** Not lab-verified; check version and privileges.
