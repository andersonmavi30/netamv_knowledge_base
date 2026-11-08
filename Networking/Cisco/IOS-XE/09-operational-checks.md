---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Operational checks — expanded · Cisco IOS XE

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** IOS XE 17.x (features vary by model). Commands have not been tested on devices; confirm syntax using `?` and release-specific docs.

## NTP synchronization peers

```text
show ntp associations | include 192.0.2
```

- **Purpose:** Inspect NTP peers and synchronization selection.
- **Parameters / flags:** associations: configured and learned NTP associations.
- **Operational use:** Check clock sync before correlating syslog timestamps.
- **Filter / check:** `show ntp associations`

## QoS counters by interface

```text
show policy-map interface GigabitEthernet1/0/1 | include drop|packets
```

- **Purpose:** Review service-policy class counters and packet drops.
- **Parameters / flags:** interface: target port; requires an applied QoS policy.
- **Operational use:** Find packet drops on a WAN QoS class.
- **Filter / check:** `show policy-map interface GigabitEthernet1/0/1 | include drop|packets`

## DHCP lease allocation

```text
show ip dhcp binding | include 192.0.2
```

- **Purpose:** Display IP-to-client lease bindings if this device runs a DHCP server.
- **Parameters / flags:** binding: current DHCP server leases.
- **Operational use:** Identify the IP leased to a client.
- **Filter / check:** `show ip dhcp binding | include 192.0.2`

## IKEv2 VPN security associations

```text
show crypto ikev2 sa | include READY|IN-NEG
```

- **Purpose:** Inspect IKEv2 SA state for supported VPN routers.
- **Parameters / flags:** ikev2 sa: negotiated control-plane SAs; feature dependent.
- **Operational use:** Find a tunnel whose IKEv2 negotiation never completed.
- **Filter / check:** `show crypto ikev2 sa | include READY|IN-NEG`

## Control-plane resource health

```text
show platform software status control-processor brief
```

- **Purpose:** Inspect control-processor CPU and memory where supported.
- **Parameters / flags:** brief: compact control processor status; platform dependent.
- **Operational use:** Verify whether management/control processes are overloaded.
- **Filter / check:** `show platform software status control-processor brief`

> ⚠️ Feature-specific commands may return no information if the feature is not configured. Stop interactive monitors when finished.

**Reference**: [Cisco IOS XE](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-xe/products-command-reference-list.html)

## QFP forwarding drops

```text
show platform hardware qfp active statistics drop
```

- **Purpose:** Display hardware forwarding drop counters on supported QFP platforms.
- **Parameters / flags:** qfp active: active forwarding processor; statistics drop: packet-drop reasons.
- **Operational use:** Investigate data-plane drops not evident from interface errors; platform-specific.
- **Reference:** https://www.cisco.com/

## BGP IPv4 neighbor summary

```text
show bgp ipv4 unicast summary
```

- **Purpose:** Display neighbor FSM and accepted prefix counts for IPv4 unicast.
- **Parameters / flags:** ipv4 unicast: address family; summary: compact peer states; BGP required.
- **Operational use:** Locate peers stuck in Active or Idle.

## Interface error counters

```text
show interfaces counters errors
```

- **Purpose:** Display receive/transmit interface error counters on supported switches.
- **Parameters / flags:** counters errors: error-only counters; availability depends on IOS-XE platform.
- **Operational use:** Identify CRC or other interface errors during packet loss.
- **Validation:** Not lab-verified; check version and privileges.

## CEF forwarding summary

```text
show ip cef summary
```

- **Purpose:** Inspect IPv4 CEF forwarding table totals and resource use where supported.
- **Parameters / flags:** summary: condensed CEF counters and entries; output depends on device.
- **Operational use:** Correlate route programming and data-plane forwarding issues.
- **Validation:** Not lab verified; confirm release and CLI context.
