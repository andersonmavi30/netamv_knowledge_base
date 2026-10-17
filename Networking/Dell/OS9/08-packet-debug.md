---
tags: [cli, dell, os9, packet-debug]
validation: not-lab-verified
---

# Packet mirroring / debug — Dell OS9

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Compatibility:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verify with `show version` and `?`.

> ⚠️ Dell has no universal CLI sniffer. Port mirroring requires a dedicated analysis port and authorization. Clean up after testing; captures may expose sensitive data.

## `monitor interface ?`

```text
monitor interface ?
```

- **Purpose:** Discover real-time interface-monitor syntax on this OS9 build.
- **Options:** ?: contextual help; not a PCAP capture.
- **Real use:** Check live counters safely.

## `show interfaces | grep CRC`

```text
show interfaces | grep CRC
```

- **Purpose:** Locate CRC counters in verbose output.
- **Options:** | grep: text filtering.
- **Real use:** Confirm physical layer issues.

## `show logging | grep OSPF`

```text
show logging | grep OSPF
```

- **Purpose:** Locate OSPF control-plane events.
- **Options:** | grep: matching events.
- **Real use:** Investigate OSPF restarts.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
