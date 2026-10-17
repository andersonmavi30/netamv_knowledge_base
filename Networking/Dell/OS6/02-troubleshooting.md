---
tags: [cli, dell, os6, troubleshooting]
validation: not-lab-verified
---

# Troubleshooting — Dell OS6

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verify with `show version` and `?`.

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Purpose:** Test reachability from the switch.
- **Options:** IP: destination.
- **Real use:** Validate gateway reachability.

## `show interfaces counters errors gigabitethernet 1/0/1`

```text
show interfaces counters errors gigabitethernet 1/0/1
```

- **Purpose:** Inspect errors on a specific port.
- **Options:** errors: error-only; port: unit/slot/port.
- **Real use:** Identify CRC or discards.

## `show spanning-tree active`

```text
show spanning-tree active
```

- **Purpose:** Inspect active spanning-tree ports.
- **Options:** active: operational instances.
- **Real use:** Investigate unexpected blocked links.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
