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
