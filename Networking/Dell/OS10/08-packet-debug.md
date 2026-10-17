---
tags: [cli, dell, os10, packet-debug]
validation: not-lab-verified
---

# Packet mirroring / debug — Dell OS10

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Compatibility:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verify with `show version` and `?`.

> ⚠️ Dell has no universal CLI sniffer. Port mirroring requires a dedicated analysis port and authorization. Clean up after testing; captures may expose sensitive data.

## `monitor session 1`

```text
configure terminal
monitor session 1
 source interface ethernet 1/1/7 rx
 destination interface ethernet 1/1/1
 no shut
 exit
end
```

- **Purpose:** Mirror ingress packets to a dedicated analysis port; connect Wireshark there.
- **Options:** rx: ingress; destination: monitor port; no shut: enable.
- **Real use:** Investigate dropped application traffic.

## `show monitor session all`

```text
show monitor session all
```

- **Purpose:** Inspect mirroring session state.
- **Options:** all: every monitoring session.
- **Real use:** Confirm session is active.

## `show interface ethernet 1/1/7 | grep error`

```text
show interface ethernet 1/1/7 | grep error
```

- **Purpose:** Find interface errors before capture.
- **Options:** | grep: match lines.
- **Real use:** Verify loss on mirrored source.

## `no monitor session 1`

```text
configure terminal
no monitor session 1
end
```

- **Purpose:** Remove the temporary monitoring session.
- **Options:** no: delete session.
- **Real use:** Clean up after authorized capture.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
