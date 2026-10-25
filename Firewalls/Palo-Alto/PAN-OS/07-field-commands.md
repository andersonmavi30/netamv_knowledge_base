---
tags: [cli, palo-alto-networks, pan-os, field-commands]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Additional field checks

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## `show arp all | match 198.51.100.1`

```text
show arp all | match 198.51.100.1
```

- **Purpose:** Filter ARP by neighbor IP.
- **Arguments:** match: text match.
- **Use case:** Validate next hop MAC on the WAN.

## `show high-availability path-monitoring | match failure`

```text
show high-availability path-monitoring | match failure
```

- **Purpose:** Search HA path monitor output for failures.
- **Arguments:** match: output filter; label may vary.
- **Use case:** Investigate failover triggered by path monitoring.

## `show ntp`

```text
show ntp
```

- **Purpose:** Display synchronization status of the firewall clock.
- **Arguments:** No pipe needed: NTP command returns targeted state.
- **Use case:** Correlate event times and session logs.

## `show lldp neighbors all | match ethernet1/2`

```text
show lldp neighbors all | match ethernet1/2
```

- **Purpose:** Filter LLDP neighbor output for the physical uplink.
- **Arguments:** match: text filter; requires LLDP enabled.
- **Use case:** Find an adjacent switch after cabling changes.

## `show routing fib virtual-router default | match 203.0.113`

```text
show routing fib virtual-router default | match 203.0.113
```

- **Purpose:** Search route to lab prefix without dumping FIB.
- **Arguments:** virtual-router: routing instance; match: prefix string.
- **Use case:** Verify expected outgoing next hop after a static route change.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
