---
tags: [cli, palo-alto-networks, pan-os, show]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## `show system info | match sw-version`

```text
show system info | match sw-version
```

- **Purpose:** Display the exact installed PAN-OS release.
- **Arguments:** match: show only lines containing `sw-version`.
- **Use case:** Check compatibility before applying a maintenance procedure.

## `show system info | match hostname`

```text
show system info | match hostname
```

- **Purpose:** Find the firewall identity without reading the entire system output.
- **Arguments:** match hostname: filters the system-information field.
- **Use case:** Confirm which firewall you reached through SSH.

## `show interface ethernet1/1`

```text
show interface ethernet1/1
```

- **Purpose:** Show status and interface statistics for the selected dataplane port.
- **Arguments:** ethernet1/1: device-dependent physical port name.
- **Use case:** Investigate the WAN port before making a change.
- **Caution:** The interface argument is already a targeted query; no extra pipe is needed.

## `show high-availability state | match State`

```text
show high-availability state | match State
```

- **Purpose:** Focus on HA state lines.
- **Arguments:** match State: case-sensitive text matching.
- **Use case:** Check active/passive state during failover investigation.
- **Caution:** Verify displayed field spelling with unfiltered command on your release.

## `show system route-table | match 0.0.0.0`

```text
show system route-table | match 0.0.0.0
```

- **Purpose:** Search management-plane routing output for a default route.
- **Arguments:** match: output text filter; 0.0.0.0: example default prefix.
- **Use case:** Distinguish management reachability from dataplane routing.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
