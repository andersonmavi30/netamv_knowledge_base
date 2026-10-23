---
tags: [cli, palo-alto-networks, pan-os, interfaces]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🔌 Interfaces & routing

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Check learned ARP for a host

```text
show arp all | match 192.0.2.10
```

- **Purpose:** Search the dataplane ARP table for a specific neighbor.
- **Parameters and filters:** all: ARP entries; match: text search.
- **Operational use:** Verify whether the next-hop MAC is learned.

## Inspect installed FIB prefix

```text
show routing fib virtual-router default | match 198.51.100
```

- **Purpose:** Find a destination prefix in the forwarding information base.
- **Parameters and filters:** virtual-router default: example VR name; match: prefix text.
- **Operational use:** Look for the selected route toward a remote network.
- **Caution:** Routing Engine / logical router deployments may use another command; verify on-device.

## Inspect optical interface status

```text
show interface ethernet1/2
```

- **Purpose:** View link and counters for a chosen interface.
- **Parameters and filters:** ethernet1/2: target dataplane port.
- **Operational use:** Check an SFP uplink that flaps.

## Check interface neighbor discovery

```text
show lldp neighbors all | match ethernet1/1
```

- **Purpose:** Search LLDP data for one port on compatible firewalls.
- **Parameters and filters:** all: all neighbor records; match: selected interface.
- **Operational use:** Identify connected switch before moving a cable.
- **Caution:** Requires LLDP to be available/enabled.

## Review interface traffic counters

```text
show counter interface ethernet1/1
```

- **Purpose:** Read hardware/interface counter values for one port.
- **Parameters and filters:** interface: choose port, no pipe required.
- **Operational use:** Investigate physical errors or drops on a WAN link.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
