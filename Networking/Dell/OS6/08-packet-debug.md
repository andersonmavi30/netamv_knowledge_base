---
tags: [cli, dell, os6, packet-debug]
validation: not-lab-verified
---

# Packet mirroring / debug — Dell OS6

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verify with `show version` and `?`.

> ⚠️ Dell has no universal CLI sniffer. Port mirroring requires a dedicated analysis port and authorization. Clean up after testing; captures may expose sensitive data.

## `show monitor session 1`

```text
show monitor session 1
```

- **Purpose:** Inspect a port mirroring session where supported.
- **Options:** 1: session ID; check monitor-session support.
- **Real use:** Send traffic to external Wireshark.

## `show statistics gigabitethernet 1/0/1`

```text
show statistics gigabitethernet 1/0/1
```

- **Purpose:** Inspect port packet statistics.
- **Options:** Port: unit/slot/port.
- **Real use:** Correlate loss before capturing.

## `show tech-support`

```text
show tech-support
```

- **Purpose:** Collect broad support diagnostics; may be sensitive.
- **Options:** No flags; output can be large.
- **Real use:** Investigate unresolved hardware issues.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
