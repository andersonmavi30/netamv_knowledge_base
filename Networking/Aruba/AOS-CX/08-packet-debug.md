---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Packet diagnostics

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify model and release.

## `mirror session 1`

```text
configure terminal
mirror session 1
source interface 1/1/2 both
destination interface 1/1/3
enable
end
```

**Verify with:**

```text
show mirror | include 1
```

- **Purpose:** Mirror test traffic to analyzer.
- **Arguments:** source: traffic; destination: monitor port.
- **Use case:** Analyze with Wireshark.

## `show mirror | include 1`

```text
show mirror | include 1
```

- **Purpose:** Check mirroring state.
- **Arguments:** include: session ID.
- **Use case:** Confirm active SPAN.

## `mirror session 1`

```text
configure terminal
mirror session 1
disable
end
```

**Verify with:**

```text
show mirror | include 1
```

- **Purpose:** Disable mirror session.
- **Arguments:** disable: stop traffic copies.
- **Use case:** Clean up capture.

## `diag utilities tshark`

```text
diagnostic
diag utilities tshark
```

- **Purpose:** Inspect traffic mirrored to CPU when supported.
- **Arguments:** tshark: interactive capture; Ctrl+C: stop.
- **Use case:** Diagnose a lab packet.

> Lab validation required. Mirror/tshark need platform support and authorization; disable after use.
