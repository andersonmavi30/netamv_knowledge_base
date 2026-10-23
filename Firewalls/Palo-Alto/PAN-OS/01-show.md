---
tags: [cli, palo-alto-networks, pan-os, show]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🔎 Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Identify installed PAN-OS version

```text
show system info | match sw-version
```

- **Purpose:** Display the exact installed PAN-OS release.
- **Parameters and filters:** match: show only lines containing `sw-version`.
- **Operational use:** Check compatibility before applying a maintenance procedure.

## Locate device hostname

```text
show system info | match hostname
```

- **Purpose:** Find the firewall identity without reading the entire system output.
- **Parameters and filters:** match hostname: filters the system-information field.
- **Operational use:** Confirm which firewall you reached through SSH.

## Inspect one physical interface

```text
show interface ethernet1/1
```

- **Purpose:** Show status and interface statistics for the selected dataplane port.
- **Parameters and filters:** ethernet1/1: device-dependent physical port name.
- **Operational use:** Investigate the WAN port before making a change.
- **Caution:** The interface argument is already a targeted query; no extra pipe is needed.

## Check HA operating state

```text
show high-availability state | match State
```

- **Purpose:** Focus on HA state lines.
- **Parameters and filters:** match State: case-sensitive text matching.
- **Operational use:** Check active/passive state during failover investigation.
- **Caution:** Verify displayed field spelling with unfiltered command on your release.

## Locate management routing information

```text
show system route-table | match 0.0.0.0
```

- **Purpose:** Search management-plane routing output for a default route.
- **Parameters and filters:** match: output text filter; 0.0.0.0: example default prefix.
- **Operational use:** Distinguish management reachability from dataplane routing.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
