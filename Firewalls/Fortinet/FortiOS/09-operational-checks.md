---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Operational checks — expanded · Fortinet FortiOS

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** FortiOS 7.x. Commands have not been tested on devices; confirm syntax using `?` and release-specific docs.

## SD-WAN SLA status

```text
diagnose sys sdwan health-check
```

- **Purpose:** Inspect latency, loss and jitter per SD-WAN health check.
- **Parameters / flags:** health-check: SD-WAN probes; optional probe name depends on release.
- **Operational use:** Investigate whether an ISP is failing its SLA.
- **Filter / check:** `diagnose sys sdwan health-check | grep -i state`

## Policy routes in the forwarding plane

```text
diagnose firewall proute list
```

- **Purpose:** Display policy routes and SD-WAN steering decisions in the data plane.
- **Parameters / flags:** proute: policy-based routing; list: entries and counters.
- **Operational use:** Check the selected egress interface for a destination.
- **Filter / check:** `diagnose firewall proute list | grep 198.51.100`

## Live process CPU inspection

```text
diagnose sys top 1 10
```

- **Purpose:** Watch the most active processes for a short troubleshooting window.
- **Parameters / flags:** 1: refresh period in seconds; 10: number of processes; q: quit interactively.
- **Operational use:** Investigate CPU spikes without enabling a packet capture.
- **Filter / check:** `Interactive: press q to quit (no pipe).`

## OSPF neighbor state

```text
get router info ospf neighbor
```

- **Purpose:** List OSPF neighbors and their current adjacency state.
- **Parameters / flags:** ospf neighbor: OSPF neighbor view; requires OSPF configuration.
- **Operational use:** Find a neighbor not reaching Full.
- **Filter / check:** `get router info ospf neighbor | grep 192.0.2`

## Link monitor health

```text
diagnose sys link-monitor status
```

- **Purpose:** Inspect link-monitor probe and failover status.
- **Parameters / flags:** status: status of configured link monitors.
- **Operational use:** Identify a failing WAN probe before changing routes.
- **Filter / check:** `diagnose sys link-monitor status | grep -i status`

> ⚠️ Feature-specific commands may return no information if the feature is not configured. Stop interactive monitors when finished.

**Reference**: [Fortinet FortiOS](https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/818746/sd-wan-related-diagnose-commands)
