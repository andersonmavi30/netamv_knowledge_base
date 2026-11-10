---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Routing protocol checks

[English](07-field-commands.md) · [Español](07-field-commands.es.md) · [Index](README.md)

**Compatibility:** Junos OS; verify model, release and `?`.

## `show ospf neighbor`

```text
show ospf neighbor
```

- **Purpose:** Display OSPF neighbors and adjacency states.
- **Arguments:** ospf neighbor: OSPF peer states; OSPF must be configured.
- **Use case:** Find a neighbor stuck outside Full state.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-ospf-neighbor.html

> Not lab-verified.

## `show bgp summary`

```text
show bgp summary
```

- **Purpose:** Display BGP peer states and received prefix summaries.
- **Arguments:** bgp summary: condensed BGP peer table; requires configured BGP.
- **Use case:** Find Idle or Active sessions before checking policy.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-bgp-summary.html

> Not lab-verified.
