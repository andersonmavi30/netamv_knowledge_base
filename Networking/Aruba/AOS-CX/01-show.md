---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Show and status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify installed release with `show version` and `?`.

## `show version | include Version`

```text
show version | include Version
```

- **Purpose:** Identify the installed AOS-CX release.
- **Arguments:** include: show matching lines.
- **Use case:** Check compatibility before maintenance.

## `show interface brief | include 1/1/1`

```text
show interface brief | include 1/1/1
```

- **Purpose:** Check one switchport status.
- **Arguments:** brief: summary; include: port filter.
- **Use case:** Diagnose a down uplink.

## `show vlan | include 10`

```text
show vlan | include 10
```

- **Purpose:** Find a VLAN by text.
- **Arguments:** include: output text match.
- **Use case:** Check VLAN 10 presence.

## `show ip route | include 198.51.100`

```text
show ip route | include 198.51.100
```

- **Purpose:** Find routes mentioning a prefix.
- **Arguments:** include: matching lines; L3 feature required.
- **Use case:** Inspect reachability to remote site.

> Examples pending lab validation; availability varies by release and hardware.

## Hardware and operating status

### `show system`

```text
show system
```

- **Purpose:** Inspect model, system status, and uptime.
- **Arguments:** system: read-only platform summary.
- **Use case:** Check status before troubleshooting or maintenance.

### `show environment temperature`

```text
show environment temperature
```

- **Purpose:** Inspect chassis and module temperature sensors.
- **Arguments:** environment temperature: sensor measurements; availability varies by model.
- **Use case:** Check status before troubleshooting or maintenance.

> Not lab-verified. AOS-CX 10.x; model/release support varies.

**Reference:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf
