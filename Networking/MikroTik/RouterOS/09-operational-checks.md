---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Operational checks — expanded · MikroTik RouterOS

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** RouterOS 7.x (model and installed features vary). Commands have not been tested on devices; confirm syntax using `?` and release-specific docs.

## MAC learning on a bridge port

```text
/interface bridge host print where on-interface="ether2"
```

- **Purpose:** Find hosts learned behind one physical port.
- **Parameters / flags:** where: property filter; on-interface: learned port.
- **Operational use:** Locate which bridge port learned a server MAC.
- **Filter / check:** `/interface bridge host print where on-interface="ether2"`

## Live BGP session details

```text
/routing bgp session print detail
```

- **Purpose:** View established BGP peers and negotiated parameters.
- **Parameters / flags:** detail: expanded session attributes; requires BGP config.
- **Operational use:** Find a peer stuck outside Established.
- **Filter / check:** `/routing bgp session print detail`

## IPsec Phase 2 SAs

```text
/ip ipsec installed-sa print detail
```

- **Purpose:** Inspect currently installed encryption SAs and counters.
- **Parameters / flags:** installed-sa: data-plane SAs; detail: expanded properties.
- **Operational use:** Check whether an IPsec tunnel actually installed SAs.
- **Filter / check:** `/ip ipsec installed-sa print detail`

## Mangle counters before routing

```text
/ip firewall mangle print stats where chain="prerouting"
```

- **Purpose:** Inspect counters of prerouting packet-mark or routing-mark rules.
- **Parameters / flags:** stats: packets/bytes; where: chain selector.
- **Operational use:** Find whether policy-routing traffic hits its mark rule.
- **Filter / check:** `/ip firewall mangle print stats where chain="prerouting"`

## Live traffic by IP and port

```text
/tool torch ether1
```

- **Purpose:** Observe talkers and traffic rates on a chosen interface.
- **Parameters / flags:** ether1: interface; interactive view; Ctrl+C exits.
- **Operational use:** Find who is saturating an uplink; may not show hardware-offloaded flows.
- **Filter / check:** `Interactive — do not append Cisco-style pipes.`

> ⚠️ Feature-specific commands may return no information if the feature is not configured. Stop interactive monitors when finished.

**Reference**: [MikroTik RouterOS](https://help.mikrotik.com/docs/spaces/ROS/pages/328134/Command+Line+Interface)
