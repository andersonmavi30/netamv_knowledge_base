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

## `show isis adjacency`

```text
show isis adjacency
```

- **Purpose:** Display IS-IS adjacencies and their operational states.
- **Arguments:** isis adjacency: neighbor and level information; requires IS-IS.
- **Use case:** Identify an IS-IS neighbor that has not established adjacency.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.

## `show vrrp detail`

```text
show vrrp detail
```

- **Purpose:** Inspect detailed VRRP group state, virtual IP and master information.
- **Arguments:** vrrp detail: expanded VRRP data; requires VRRP configured.
- **Use case:** Confirm VRRP master and backup roles during failover.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.

## `show rsvp neighbor`

```text
show rsvp neighbor
```

- **Purpose:** List RSVP neighbor relationships and connection status.
- **Arguments:** rsvp neighbor: RSVP neighbor data; requires RSVP configuration.
- **Use case:** Check signaling neighbors during an MPLS traffic engineering issue.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Not lab-verified.
