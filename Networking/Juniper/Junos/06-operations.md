---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Operational checks

[English](06-operations.md) · [Español](06-operations.es.md) · [Index](README.md)

**Compatibility:** Junos OS; verify model, release and `?`.

## `show route summary`

```text
show route summary
```

- **Purpose:** Summarize routing table sizes and route counts.
- **Arguments:** route: routing information; summary: counts by routing table.
- **Use case:** Identify unexpected routing table growth.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-route.html

> Not lab-verified.

## `show lldp neighbors`

```text
show lldp neighbors
```

- **Purpose:** List LLDP neighbors and their connected local interfaces.
- **Arguments:** lldp neighbors: discovered neighbor table; requires LLDP enabled.
- **Use case:** Identify the device connected to an uplink.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-lldp-neighbors.html

> Not lab-verified.

## `show ethernet-switching table`

```text
show ethernet-switching table
```

- **Purpose:** Display dynamically learned Layer 2 MAC address entries.
- **Arguments:** ethernet-switching table: MAC learning database; switching platforms only.
- **Use case:** Find an endpoint MAC and associated VLAN/interface.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-ethernet-switching-table.html

> Not lab-verified.

## `show system core-dumps`

```text
show system core-dumps
```

- **Purpose:** Display available system core dump files for process crash investigation.
- **Arguments:** system core-dumps: list crash dumps; does not create new dumps.
- **Use case:** Check whether a daemon crash produced diagnostic evidence.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.

## `show system license`

```text
show system license
```

- **Purpose:** Display installed system licenses and their validity information.
- **Arguments:** system license: licensing status; fields depend on platform.
- **Use case:** Verify licensing before investigating a feature that is unavailable.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.
