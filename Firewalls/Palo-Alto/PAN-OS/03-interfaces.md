---
tags: [cli, palo-alto-networks, pan-os, interfaces]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Interfaces & routing

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## `show arp all | match 192.0.2.10`

```text
show arp all | match 192.0.2.10
```

- **Purpose:** Search the dataplane ARP table for a specific neighbor.
- **Arguments:** all: ARP entries; match: text search.
- **Use case:** Verify whether the next-hop MAC is learned.

## `show routing fib virtual-router default | match 198.51.100`

```text
show routing fib virtual-router default | match 198.51.100
```

- **Purpose:** Find a destination prefix in the forwarding information base.
- **Arguments:** virtual-router default: example VR name; match: prefix text.
- **Use case:** Look for the selected route toward a remote network.
- **Caution:** Routing Engine / logical router deployments may use another command; verify on-device.

## `show interface ethernet1/2`

```text
show interface ethernet1/2
```

- **Purpose:** View link and counters for a chosen interface.
- **Arguments:** ethernet1/2: target dataplane port.
- **Use case:** Check an SFP uplink that flaps.

## `show lldp neighbors all | match ethernet1/1`

```text
show lldp neighbors all | match ethernet1/1
```

- **Purpose:** Search LLDP data for one port on compatible firewalls.
- **Arguments:** all: all neighbor records; match: selected interface.
- **Use case:** Identify connected switch before moving a cable.
- **Caution:** Requires LLDP to be available/enabled.

## `show counter interface ethernet1/1`

```text
show counter interface ethernet1/1
```

- **Purpose:** Read hardware/interface counter values for one port.
- **Arguments:** interface: choose port, no pipe required.
- **Use case:** Investigate physical errors or drops on a WAN link.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
