---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Show and system status

[English](01-show.md) · [Español](01-show.es.md) · [Index](README.md)

**Compatibility:** Junos OS; verify with `show version` and `?`; varies among EX/QFX/MX/SRX.

## `show version`

```text
show version
```

- **Purpose:** Display Junos OS release, model and software information.
- **Arguments:** version: full software inventory; optional output filters can narrow it.
- **Use case:** Verify OS version before checking feature support.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-version.html

> Not lab-verified.

## `show chassis alarms`

```text
show chassis alarms
```

- **Purpose:** Display active chassis alarms and severity.
- **Arguments:** chassis: hardware subsystem; alarms: active alarm list.
- **Use case:** Identify hardware issues before planned maintenance.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-chassis-alarms.html

> Not lab-verified.

## `show system uptime`

```text
show system uptime
```

- **Purpose:** Display current time, boot uptime and protocol start times where provided.
- **Arguments:** system uptime: operational clock and uptime; fields vary with Junos release.
- **Use case:** Correlate a reported outage with the most recent reboot.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.

## `show chassis hardware extensive`

```text
show chassis hardware extensive
```

- **Purpose:** Display detailed chassis, FRU and hardware identification information.
- **Arguments:** chassis hardware: inventory; extensive: expanded hardware details.
- **Use case:** Inspect component identifiers before replacing faulty hardware.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.

## `show chassis routing-engine`

```text
show chassis routing-engine
```

- **Purpose:** Display Routing Engine health, memory and CPU utilization.
- **Arguments:** chassis routing-engine: RE metrics; fields depend on platform.
- **Use case:** Check control-plane load when routing protocols respond slowly.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.
