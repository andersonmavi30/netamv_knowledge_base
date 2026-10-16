---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Packet capture & debugging — Cisco IOS XE

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference version:** IOS XE (EPC supported on suitable hardware/release).

> ⚠️ Captures and debugging may consume resources or expose sensitive data. Use only on authorized networks, scope carefully and always stop afterward.

## monitor capture LAB interface GigabitEthernet0/0/1 both

```text
monitor capture LAB interface GigabitEthernet0/0/1 both
monitor capture LAB match ipv4 host 192.0.2.10 any
monitor capture LAB start
```

- **Purpose:** Set a capture on one interface with an IPv4 host filter.
- **Parameters:** both: both directions; match: capture filter; start: begin.
- **Real-world use:** Trace packets sourced by a lab host (check match syntax on the release).

## monitor capture LAB stop

```text
monitor capture LAB stop
show monitor capture LAB buffer brief
no monitor capture LAB
```

- **Purpose:** Stop capture, inspect packet summary and remove it.
- **Parameters:** stop: stop collection; buffer brief: packet list; no: delete capture.
- **Real-world use:** Finish packet analysis without leaving a capture enabled.

## show monitor capture LAB parameter

```text
show monitor capture LAB parameter
```

- **Purpose:** Verify EPC parameters before collecting traffic.
- **Parameters:** parameter: display configured interface, match and buffer values.
- **Real-world use:** Check which interface/filter the capture will actually use.

**Vendor reference:** https://www.cisco.com/c/en/us/support/docs/ios-nx-os-software/ios-embedded-packet-capture/116045-productconfig-epc-00.html

**Note:** EPC/sniffer may not see hardware-offloaded packets. Protocol debugging is not the same as PCAP.
