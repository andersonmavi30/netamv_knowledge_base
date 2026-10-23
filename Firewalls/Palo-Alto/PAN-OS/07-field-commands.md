---
tags: [cli, palo-alto-networks, pan-os, field-commands]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🧰 Additional field checks

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Find ARP entry by IP

```text
show arp all | match 198.51.100.1
```

- **Purpose:** Filter ARP by neighbor IP.
- **Parameters and filters:** match: text match.
- **Operational use:** Validate next hop MAC on the WAN.

## Find HA monitored path failures

```text
show high-availability path-monitoring | match failure
```

- **Purpose:** Search HA path monitor output for failures.
- **Parameters and filters:** match: output filter; label may vary.
- **Operational use:** Investigate failover triggered by path monitoring.

## Check NTP state

```text
show ntp
```

- **Purpose:** Display synchronization status of the firewall clock.
- **Parameters and filters:** No pipe needed: NTP command returns targeted state.
- **Operational use:** Correlate event times and session logs.

## Find management-related interface neighbors

```text
show lldp neighbors all | match ethernet1/2
```

- **Purpose:** Filter LLDP neighbor output for the physical uplink.
- **Parameters and filters:** match: text filter; requires LLDP enabled.
- **Operational use:** Find an adjacent switch after cabling changes.

## Inspect one installed route in the FIB

```text
show routing fib virtual-router default | match 203.0.113
```

- **Purpose:** Search route to lab prefix without dumping FIB.
- **Parameters and filters:** virtual-router: routing instance; match: prefix string.
- **Operational use:** Verify expected outgoing next hop after a static route change.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
